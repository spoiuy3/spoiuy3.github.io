<style>
  .pub-badge-wrap {
    position: absolute;
    top: 10px;
    left: 20px;
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
    z-index: 10;
  }

  .pub-badge-wrap .badge {
    position: static !important;
    margin: 0;
    padding: 4px 8px;
    font-size: 11px;
    line-height: 1.2;
    border-radius: 6px;
    font-weight: 600;
    display: inline-block;
  }

  .pub-badge-wrap .conf-badge {
    background-color: #333;
    color: #fff;
  }

  .pub-badge-wrap .highlight-badge {
    background: linear-gradient(135deg, #ff7b72, #ffb347);
    color: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.15);
  }
</style>

<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width:100%; height:auto;">

    {% if link.conference_short or link.highlight %}
    <div class="pub-badge-wrap">
      {% if link.conference_short %}
      <abbr class="badge conf-badge">{{ link.conference_short }}</abbr>
      {% endif %}

      {% if link.highlight %}
      <abbr class="badge highlight-badge">✨ Highlight</abbr>
      {% endif %}
    </div>
    {% endif %}

    {% endif %}
  </div>

  <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">
    <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
    <div class="author">{{ link.authors }}</div>
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
      {% if link.notes %} 
      <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>
<br>

{% endfor %}

</ol>
</div>