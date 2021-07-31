# Varbase Sub Profile Basic Template

Download it from: [https://github.com/Vardot/varbase\_subprofile\_basic](https://github.com/Vardot/varbase_subprofile_basic)

## Managing Installation Steps for Varbase sub profiles

Managing the custom ConfigBits:

**default.components.varbase\_subprofile\_basic.bit.yml**

Which it could be a copy of [Varbase default components](https://github.com/Vardot/varbase/blob/8.x-4.x/configbit/default.components.varbase.bit.yml)

```text
# ==============================================================================
# List of default varbase sub profile basic components, which they will be
# installed when we install varbase.
# ==============================================================================
config_bit:
  type: list
  for: varbase_subprofile_basic.info.yml
  when:
    install_default_components: true
    list:
      dependencies:
        # Enable listed Varbase modules in order at this installation step.
        - varbase_core
        - varbase_media
        - varbase_editor
        - varbase_admin
        - varbase_email
        - varbase_security
        - varbase_seo
        - varbase_workflow
        - varbase_layout_builder
        - vlplb
        # Enable default varbase sub profile basic features.
        - varbase_subprofile_basic_homepage
#        - varbase_subprofile_basic_CUSTOM_FEATRE_01
#        - varbase_subprofile_basic_CUSTOM_FEATRE_02
#        - varbase_subprofile_basic_CUSTOM_FEATRE_03
#        - varbase_subprofile_basic_CUSTOM_FEATRE_04

```

**extra.components.varbase\_subprofile\_basic.bit.yml**

Which it could be a copy of

[extra varbase components](https://github.com/Vardot/varbase/blob/8.x-4.x/configbit/extra.components.varbase.bit.yml)

```text
# ==============================================================================
# List of VARBASE_SUBPROFILE_BASIC demo components, which they will be listed under the 
# Extra components installation step, in the Demo content section.
# ==============================================================================
config_bit:
  type: list
  for: varbase_subprofile_basic.info.yml
  when:
    show_demo: true
    list:
      dependencies:
        varbase_subprofile_basic_demo:
          title: "Install Varbase Subprofile Demo Content"
          description: "If you're evaluating Varbase Subprofile, installing demo content will help you get an idea of how Varbase Subprofile works, and what features are included."
          selected: false
          config_form: false

```

**demo.content.varbase\_subprofile\_basic.bit.yml**

Which it could be a copy of

[varbase demo components](https://github.com/Vardot/varbase/blob/8.x-4.x/configbit/demo.content.varbase.bit.yml)

```text
# ==============================================================================
# List of varbase_subprofile_basic extra components, which they will be listed
# in the Extra feature form, when we install varbase subprofile basic.
# ==============================================================================
config_bit:
  type: list
  for: varbase_subprofile_basic.info.yml
  when:
    show_extra_components: true
    list:
      dependencies:
        varbase_media_header:
          title: "Varbase Media Header"
          description: "Populates the universal media header style on top of web pages. Which lets site builders activate that for content types."
          selected: false
          config_form: false
        varbase_search:
          title: "Varbase Search"
          description: "A suite of site search engine tools to help you build better search performance, customization, and search experience. Built using <a href=\"https://www.drupal.org/project/search_api\" target=\"_blank\">Search API</a>."
          selected: false
          config_form: false
```

