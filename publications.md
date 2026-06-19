---
layout: homepage
---

<div class="page-tabs">
  <a class="tab" href="{{ '/' | relative_url }}">Home</a>
  <a class="tab active" href="{{ '/publications.html' | relative_url }}">Publications</a>
  <a class="tab" href="{{ '/projects.html' | relative_url }}">Projects</a>
</div>

{% include_relative _includes/publications.md heading="Scientific Machine Learning" category="scientific machine learning" section_title="" %}

{% include_relative _includes/publications.md heading="Computational Fluid Dynamics & Combustion" category="computational fluid dynamics and combustion" section_title="" %}
