---
layout: default
title: Comparison Matrix
permalink: /matrix/
---

# Comparison Matrix

Documents as rows, issuers as columns. Each cell links to the rendered exhibit.
Comparable documents across filings can be redlined against each other —
expected differences are variable substitutions; unexpected differences are signal.

<table class="matrix-table">
  <thead>
    <tr>
      <th>Document</th>
      {% for filing in site.data.filings %}
        <th>{{ filing.company | split: " " | first }} {{ filing.filing_type }}</th>
      {% endfor %}
    </tr>
  </thead>
  <tbody>
    {% for doc_type in site.data.document_types %}
    <tr>
      <td>{{ doc_type.title }}</td>
      {% for filing in site.data.filings %}
        {% assign match = nil %}
        {% for page in site.filings %}
          {% if page.filing_id == filing.id and page.document_type == doc_type.id %}
            {% assign match = page %}
          {% endif %}
        {% endfor %}
        <td>
          {% if match %}
            <a href="{{ match.url | relative_url }}">View</a>
          {% else %}
            —
          {% endif %}
        </td>
      {% endfor %}
    </tr>
    {% endfor %}
  </tbody>
</table>
