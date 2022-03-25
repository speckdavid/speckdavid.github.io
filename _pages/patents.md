---
layout: page
permalink: /patents/
title: Patents
description:
years: [2021,2020]
nav: true
---
<!-- _pages/patents.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f patents -q @*[year={{y}}]* %}
{% endfor %}

</div>
