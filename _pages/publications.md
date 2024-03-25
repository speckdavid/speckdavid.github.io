---
layout: page
permalink: /publications/
title: Publications
description:
years: [2024,2023,2022,2021,2020,2019,2018,2017,2015]
nav: true
---
<!-- _pages/publications.md -->

<div class="publications">

<div class="toggle-container">
  <label class="switch">
    <input type="checkbox" id="toggle">
    <span class="slider"></span>
  </label>
  <span class="toggle-label">Superseded papers</span>
</div>

<div id="content-off">
  {%- for y in page.years %}
    <h2 class="year">{{y}}</h2>
    {% bibliography -f papers -q @*[year={{y}}]* %}
  {% endfor %}
</div>

<div id="content-on" style="display: none;">
  {%- for y in page.years %}
    <h2 class="year">{{y}}</h2>
    {% bibliography -f papers -q @*[year={{y}}]* %}
    {% bibliography -f papers_superseded -q @*[year={{y}}]* %}
  {% endfor %}
</div>

<script>
  // Initialize the toggle state when the page loads or is navigated to
  document.addEventListener("DOMContentLoaded", function () {
    const toggle = document.getElementById("toggle");
    const contentOn = document.getElementById("content-on");
    const contentOff = document.getElementById("content-off");

    // Retrieve toggle state from local storage
    const storedToggleState = localStorage.getItem("toggleState");

    // Set initial toggle state based on stored value or default
    toggle.checked = storedToggleState === "on";
    contentOn.style.display = toggle.checked ? "block" : "none";
    contentOff.style.display = toggle.checked ? "none" : "block";

    // Add event listener to handle toggle change
    toggle.addEventListener("change", () => {
      if (toggle.checked) {
        contentOn.style.display = "block";
        contentOff.style.display = "none";
      } else {
        contentOn.style.display = "none";
        contentOff.style.display = "block";
      }

      // Store toggle state in local storage
      localStorage.setItem("toggleState", toggle.checked ? "on" : "off");
    });
  });
</script>

</div>
