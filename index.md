---
layout: default
---

{% assign redirects = site.urls | where_exp: "item", "item.redirect_to != nil" %}

<table>

{% for page in redirects %}

<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">
      
[{{ page.url }}]({{ page.url | relative_url }})

    </h5>
    <p class="card-text">
    
{{ page.description }}

    </p>
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">
      
[{{ page.url }}]({{ page.url | relative_url }})
      
    </li>
    <li class="list-group-item"><a onclick="CopyToClipboard([{{ page.url }}]);">Copy link to clipboard</a></li>
  </ul>
</div>

{% endfor %}
</table>

<script>function CopyToClipboard(parameter) {navigator.clipboard.writeText(parameter);}</script>
