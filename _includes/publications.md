<h1 id="publications"></h1>

<h2 style="margin: 60px 0px 10px;">Publications</h2>

<h4 style="margin:0 10px 0;">
    <img src="../assets/img/Honorable_Mention.png" alt="icon" style="width:15px; height:15px; vertical-align:middle;">&nbsp;&nbsp;Honorable Mention
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <img src="../assets/img/mail.png" alt="Corresponding Author" style="width: 15px; height: auto; vertical-align: middle;">&nbsp;&nbsp;Corresponding Author
</h4>

<!-- <h2 style="margin: 60px 0px -15px;">Publications <temp style="font-size:15px;">[</temp><a href="https://scholar.google.com/citations?user=Qi2PSmEAAAAJ" target="_blank" style="font-size:15px;">Google Scholar</a><temp style="font-size:15px;">]</temp><temp style="font-size:15px;">[</temp><a href="https://dblp.org/pid/12/10033-1.html" target="_blank" style="font-size:15px;">DBLP</a><temp style="font-size:15px;">]</temp></h2> -->

<div class="publications">

{% assign grouped_pubs = site.data.publications.main | group_by: "year" | sort: "name" | reverse %}

{% for group in grouped_pubs %}

  <h3 style="margin: 30px 0px 10px;">{{ group.name }}</h3>

  <ol class="bibliography">
    {% for link in group.items %}
    
    <li>
      <div class="pub-row">
        <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
        {% if link.image %}
          <img
            src="{{ link.image }}"
            class="teaser img-fluid z-depth-1"
            loading="lazy"
            decoding="async"
            width="320"
            height="180"
            style="width: 100%; height: auto; aspect-ratio: 16 / 9; object-fit: cover;"
            alt="Teaser for {{ link.conference_short }}: {{ link.title | strip_html | escape }}"
          >
        {% endif %}
          <abbr class="badge">{{ link.conference_short }}</abbr>
        </div>
        <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
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
            {% if link.supp %} 
            <a href="{{ link.supp }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Supp</a>
            {% endif %}
            {% if link.supp2 %} 
            <a href="{{ link.supp2 }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Supp2</a>
            {% endif %}
            {% if link.video %} 
            <a href="{{ link.video }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Video</a>
            {% endif %}
            {% if link.page %} 
            <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Page</a>
            {% endif %}
            {% if link.data %} 
            <a href="{{ link.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Dataset</a>
            {% endif %}
            {% if link.bibtex %} 
            <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
            {% endif %}
            {% if link.notes %} 
            <strong> <i style="color:#e74d3c; font-weight:600">{{ link.notes }}</i></strong>
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

{% endfor %}

</div>
