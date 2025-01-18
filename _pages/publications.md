---
layout: page
permalink: /publications/
title: Publications
description: Publications from Dice Group
years: [2025, 2024, 2023, 2022, 2021, 2020, 2019]
nav: true
order: 1
---

<!-- <b>SAILING Members:</b> If you want to add your publications to this page, please refer to the <a href="https://github.com/sailing-lab/sailing-lab.github.io/blob/main/docs/publications.md">instruction</a>. -->

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>