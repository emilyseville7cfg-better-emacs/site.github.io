---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

# Summary

This site is all about Emacs extensions enhancing its experience.
Tired of reimplementing routine stuff again and again?
Then we can suggest you our extensions to resolve this problem. 😄
Down below we list all our extensions being split by categories.

## Requirenments

All extensions require `Emacs 27.1` or higher.

## Packages

{% for package in site.data.packages %}
- **Question**: {{ package.question }}
  
  **Answer**: Try out [`{{ package.package }}`](https://github.com/emilyseville7cfg-better-emacs/{{ package.package }}) extension.
{% if package.note %}
  **Note**: {{ package.note }}
{% endif %}
{% endfor %}
