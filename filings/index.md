---
layout: default
title: All Filings
permalink: /filings/
---

# All Filings

<ul class="filing-list">
{% for filing in site.data.filings %}
  <li>
    <a href="{{ '/filings/' | append: filing.id | append: '/' | relative_url }}">{{ filing.company }} — {{ filing.filing_type }}</a>
    <div class="filing-meta">
      {{ filing.counsel }} · {{ filing.underwriter }} · {{ filing.filing_date }}
      {% if filing.edgar_url != "" %}
        · <a href="{{ filing.edgar_url }}">EDGAR</a>
      {% endif %}
    </div>
  </li>
{% endfor %}
</ul>
