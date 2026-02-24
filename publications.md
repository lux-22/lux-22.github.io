---
layout: homepage
---

<div class="page-tabs">
  <a class="tab" href="{{ '/' | relative_url }}">Home</a>
  <a class="tab active" href="{{ '/publications.html' | relative_url }}">Publications</a>
  <a class="tab" href="{{ '/projects.html' | relative_url }}">Projects</a>
</div>

{% include_relative _includes/publications.md heading="Publications" flatten=true %}
