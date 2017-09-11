# Varbase Sub Profile Basic Template

Download it from:
https://bitbucket.org/Vardot/varbase_subprofile_basic


### Managing Installation Steps for Varbase sub profiles

By managing your custom ConfigBits:


**default.components.varbase_subprofile_basic.bit.yml**


Which it could be a copy of [Varbase default components](https://github.com/Vardot/varbase/blob/8.x-4.x/configbit/default.components.varbase.bit.yml)


```
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
        - varbase_core
        - varbase_admin
        - varbase_total_control
        - varbase_security
        - varbase_seo
        - varbase_editor
        - varbase_media
        - varbase_webform
        - varbase_page
        - varbase_landing
        # Enable listed modules in order at this installation step.
        - libraries
        # Enable default varbase sub profile basic base modules and features.
        - vmi
        - varbase_heroslider_media
        - varbase_carousels
        # Enable default varbase sub profile basic features.
#        - varbase_subprofile_basic_CUSTOM_FEATRE_01
#        - varbase_subprofile_basic_CUSTOM_FEATRE_02
#        - varbase_subprofile_basic_CUSTOM_FEATRE_03
#        - varbase_subprofile_basic_CUSTOM_FEATRE_04 

```




**extra.components.varbase_subprofile_basic.bit.yml**


Which it could be a copy of

  [extra varbase components](https://github.com/Vardot/varbase/blob/8.x-4.x/configbit/extra.components.varbase.bit.yml)



```
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
        varbase_search:
          title: "Varbase Search"
          description: "A suite of site search engine tools to help you build better search performance, customization, and search experience. Built using <a href=\"https://www.drupal.org/project/search_api\" target=\"_blank\">Search API</a>."
          selected: false
          config_form: false
```





**demo.content.varbase_subprofile_basic.bit.yml**

Which it could be a copy of

  [varbase demo components](https://github.com/Vardot/varbase/blob/8.x-4.x/configbit/demo.content.varbase.bit.yml)


```
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