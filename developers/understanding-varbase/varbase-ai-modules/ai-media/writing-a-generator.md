# Writing a Generator Plugin

Each kind of generated media is an `#[AiMediaGenerator]` plugin in a module's `src/Plugin/AiMediaGenerator`. The settings map it to one of the site's media types, so a new kind of media is a new plugin, not a fork.

## The Plugin

```php
namespace Drupal\my_module\Plugin\AiMediaGenerator;

use Drupal\ai\OperationType\TextToImage\TextToImageInput;
use Drupal\ai_media\AiMediaGeneratorBase;
use Drupal\ai_media\Attribute\AiMediaGenerator;
use Drupal\ai_media\GeneratedFile;
use Drupal\Core\StringTranslation\TranslatableMarkup;

#[AiMediaGenerator(
  id: 'icon',
  label: new TranslatableMarkup('Icon'),
  tab_label: new TranslatableMarkup('Generate icon with AI'),
  media_source: 'image',
  operation_types: ['text_to_image'],
  file_extensions: ['png'],
  description: new TranslatableMarkup('A square icon from a description.'),
  weight: 15,
)]
class Icon extends AiMediaGeneratorBase {

  // The editor options the settings may show for it.
  protected const EDITOR_OPTIONS = ['models', 'size', 'format'];

  protected function doGenerate(string $description, array $options): GeneratedFile {
    [$provider, $model] = $this->providerFor('text_to_image', [
      'size' => $this->sizeFor('text_to_image', $options['shape']),
    ]);
    $image = $provider->textToImage(new TextToImageInput($description), $model, ['ai_media'])
      ->getNormalized()[0];
    return new GeneratedFile($image->getBinary(), 'image/png', 'png');
  }

}
```

## What the Attribute Says

| Key | Meaning |
| --- | --- |
| `media_source` | The core media source it makes files for, such as `image`, `video_file` or `file`. Only media types with this source can be mapped to it. |
| `operation_types` | The AI operations it calls, in order. Each needs a provider (see [Providers](providers.md)) or the generator is not set up. |
| `file_extensions` | What it writes. The mapped media type's field must allow at least one. |
| `tab_label` | The **Media Library** tab, an action, used when the generators are shown as tabs of their own. |
| `weight` | Order among the generators. |

## What the Base Class Does for You

- `providerFor($operation, $wanted)` returns the provider and model the editor picked, else the AI module default for that operation, configured with only the options the model has and accepts.
- `generate()` checks and fills the editor options first: `$options['shape']`, `quality` and `format` always hold an allowed value, and `sizeFor()` turns a shape into the closest size the model lists.
- `buildOptions()` is for options of your own, such as the SVG style.
- `generate()` refuses when the generator is not offered or not set up, logs any failure on the `ai_media` channel and turns it into one message for the current user. Throw `GenerationException` yourself for a message of your own.
- `isOffered()`, `isConfigured()`, `providerLabel()` and `notConfiguredMessage()` are already implemented.

## The Result

`GeneratedFile` carries the bytes, the MIME type and the extension, plus optional `previewText` (shown in the review step for files a thumbnail cannot show) and `title` (used as the media name). The form saves it as a temporary file where the field (or the settings) say, checks the extension and the size, and puts it in the review step.

{% hint style="warning" %}
Anything the model wrote that will be served as markup must be sanitized: see how the **SVG** generator parses, sanitizes and refuses rather than repairs, in [SVG and Animated SVG](svg-and-animated-svg.md#safety).
{% endhint %}

A new generator has no media type until a site sets one: on the settings page, with the `setAiMediaTypes` config action, or in your module's `config/defaults/ai_media.settings.yml` (`generators.<id>.media_type`). In AI mode the **Media Library** builds **AI Media**'s form for that type, whatever upload form its source has; **Upload** keeps that upload form.

Implementations can alter generator definitions with `hook_ai_media_generator_info_alter()`.
