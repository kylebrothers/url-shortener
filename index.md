---
layout: default
---

{% assign redirects = site.urls | where_exp: "item", "item.redirect_to != nil" %}

| Link        | Copy Link   | Description   |
| :---        |    :----:   |          ---: |
{% for page in redirects %}
  |[{{ page.url }}]({{ page.url | relative_url }})|<button class="mui-btn mui-btn--primary mui-btn--flat mui-col-md-1" onclick="CopyToClipboard('https://helpmencri.org/MDSA');"><span class="material-symbols-sharp">content_copy</span></button>|{{ description }}|

{% endfor %}

<script>function CopyToClipboard(parameter) {navigator.clipboard.writeText(parameter);}</script>
