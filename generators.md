---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

title: generators
layout: page
---

{% for code_example in site.data.generators %}
## {{ code_example.original.description }}

```{{ code_example.original.language }}
{{ code_example.original.code -}}
```
{%- for translated_code_example in code_example.translations %}
{% assign description = translated_code_example.description %}
{% assign show_description = true %}
{% if description == "inherit" %}
{% assign description = code_example.original.description %}
{% assign show_description = false %}
{% endif %}
{% if show_description %}
### {{ description }}
{% endif %}
{% assign required_imports = translated_code_example.imports | join: ", " %}
{% assign required_imports_note = "" %}
{% if required_imports != "" %}
{% assign required_imports_note = " (required imports: " | append: required_imports | append: ")" %}
{% endif %}
Equivalent {{ translated_code_example.language | capitalize }} code{{ required_imports_note }}:
```{{ translated_code_example.language }}
{{ translated_code_example.code -}}
```
{%- endfor %}
{% endfor %}
