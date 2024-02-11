---
layout: default
---

{% assign redirects = site.urls | where_exp: "item", "item.redirect_to != nil" %}

<table>

  {% for page in redirects %}
  <tr class="row1">
    <td class="col1">
      [{{ page.url }}]({{ page.url | relative_url }})
    </td>
    <td class="col2">
      <button onclick="CopyToClipboard([{{ page.url }}]);"><span>content_copy</span></button>
    </td>
    <td class="col3">
      {{ description }}
    </td>
  </tr>

{% endfor %}
</table>

<script>function CopyToClipboard(parameter) {navigator.clipboard.writeText(parameter);}</script>
