---
layout: default
title: Redliner — Sample Filings
---

# Sample Filings

SEC registration statements for SPAC IPOs, organized for cross-filing comparison.
All filings below share common counsel (Loeb & Loeb) and underwriter (Cantor Fitzgerald),
making them ideal for redline analysis — the documents *should* be structurally identical,
with differences limited to variable substitutions (company name, dates, amounts).

<ul class="filing-list">
{% for filing in site.data.filings %}
  <li>
    <a href="{{ '/filings/' | append: filing.id | append: '/' | relative_url }}">{{ filing.company }} — {{ filing.filing_type }}</a>
    <div class="filing-meta">
      {{ filing.counsel }} · {{ filing.underwriter }} · {{ filing.filing_date }}
    </div>
  </li>
{% endfor %}
</ul>
