{% assign heading = include.heading | default: "Publications" %}
{% assign sci_ml = site.data.publications.main | where: "category", "scientific machine learning" %}
{% assign cfd = site.data.publications.main | where: "category", "computational fluid dynamics and combustion" %}

{% if include.show_heading != false %}
<h2 id="publications" style="margin: 2px 0px -15px;">{{ heading }}</h2>
{% endif %}

<div class="publications">
{% if include.flatten %}
  <ol class="bibliography">
  {% for link in site.data.publications.main %}

  <li class="pub-item">
    <div class="pub-content">
      <div class="title">
        {% if link.pdf %}
        <a href="{{ link.pdf }}">{{ link.title }}</a>
        {% else %}
        {{ link.title }}
        {% endif %}
        {% if link.conference_short %}
        <span class="badge pub-badge">{{ link.conference_short }}</span>
        {% endif %}
      </div>
      <div class="author">
        {{ link.authors }}{% if link.notes %} {{ link.notes }}{% endif %}
      </div>
      <div class="periodical"><em>{{ link.conference }}</em></div>
      <div class="links">
        {% if link.pdf %}
        <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
        {% endif %}
        {% if link.code %}
        <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
        {% endif %}
        {% if link.page %}
        <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
        {% endif %}
        {% if link.bibtex %}
        <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
        {% endif %}
        {% if link.others %}
        {{ link.others }}
        {% endif %}
      </div>
    </div>
  </li>

  {% endfor %}
  </ol>
{% elsif include.category %}
  {% assign filtered = site.data.publications.main | where: "category", include.category %}
  {% assign section_title = include.section_title %}
  {% if section_title == nil and include.category == "scientific machine learning" %}
    {% assign section_title = "Scientific Machine Learning" %}
  {% endif %}
  {% if section_title and section_title != "" %}
  <h3 class="pub-section">{{ section_title }}</h3>
  {% endif %}
  <ol class="bibliography">
  {% for link in filtered %}

  <li class="pub-item">
    <div class="pub-content">
      <div class="title">
        {% if link.pdf %}
        <a href="{{ link.pdf }}">{{ link.title }}</a>
        {% else %}
        {{ link.title }}
        {% endif %}
        {% if link.conference_short %}
        <span class="badge pub-badge">{{ link.conference_short }}</span>
        {% endif %}
      </div>
      <div class="author">
        {{ link.authors }}{% if link.notes %} {{ link.notes }}{% endif %}
      </div>
      <div class="periodical"><em>{{ link.conference }}</em></div>
      <div class="links">
        {% if link.pdf %}
        <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
        {% endif %}
        {% if link.code %}
        <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
        {% endif %}
        {% if link.page %}
        <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
        {% endif %}
        {% if link.bibtex %}
        <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
        {% endif %}
        {% if link.others %}
        {{ link.others }}
        {% endif %}
      </div>
    </div>
  </li>

  {% endfor %}
  </ol>
{% else %}
  <h3 class="pub-section">Scientific Machine Learning</h3>
  <ol class="bibliography">
  {% for link in sci_ml %}

  <li class="pub-item">
    <div class="pub-content">
      <div class="title">
        {% if link.pdf %}
        <a href="{{ link.pdf }}">{{ link.title }}</a>
        {% else %}
        {{ link.title }}
        {% endif %}
        {% if link.conference_short %}
        <span class="badge pub-badge">{{ link.conference_short }}</span>
        {% endif %}
      </div>
      <div class="author">
        {{ link.authors }}{% if link.notes %} {{ link.notes }}{% endif %}
      </div>
      <div class="periodical"><em>{{ link.conference }}</em></div>
      <div class="links">
        {% if link.pdf %}
        <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
        {% endif %}
        {% if link.code %}
        <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
        {% endif %}
        {% if link.page %}
        <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
        {% endif %}
        {% if link.bibtex %}
        <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
        {% endif %}
        {% if link.others %}
        {{ link.others }}
        {% endif %}
      </div>
    </div>
  </li>

  {% endfor %}
  </ol>

  <h3 class="pub-section">CFD, combustion, and fire</h3>
  <ol class="bibliography">
  {% for link in cfd %}

  <li class="pub-item">
    <div class="pub-content">
      <div class="title">
        {% if link.pdf %}
        <a href="{{ link.pdf }}">{{ link.title }}</a>
        {% else %}
        {{ link.title }}
        {% endif %}
        {% if link.conference_short %}
        <span class="badge pub-badge">{{ link.conference_short }}</span>
        {% endif %}
      </div>
      <div class="author">
        {{ link.authors }}{% if link.notes %} {{ link.notes }}{% endif %}
      </div>
      <div class="periodical"><em>{{ link.conference }}</em></div>
      <div class="links">
        {% if link.pdf %}
        <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
        {% endif %}
        {% if link.code %}
        <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
        {% endif %}
        {% if link.page %}
        <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
        {% endif %}
        {% if link.bibtex %}
        <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
        {% endif %}
        {% if link.others %}
        {{ link.others }}
        {% endif %}
      </div>
    </div>
  </li>

  {% endfor %}
  </ol>
{% endif %}
</div>
