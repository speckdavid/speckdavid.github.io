---
layout: page
permalink: /publications/
title: Publications
description:
years: [2025, 2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2015]
nav: true
---
<!-- _pages/publications.md -->

<div class="publications">

<div class="toggle-container">
  <label class="switch">
    <input type="checkbox" id="conference-toggle" checked>
    <span class="slider"></span>
  </label>
  <span class="toggle-label">Conference publications</span>
</div>
<div class="toggle-container">
  <label class="switch">
    <input type="checkbox" id="journal-toggle" checked>
    <span class="slider"></span>
  </label>
  <span class="toggle-label">Journal publications</span>
</div>
<div class="toggle-container">
  <label class="switch">
    <input type="checkbox" id="workshop-toggle">
    <span class="slider"></span>
  </label>
  <span class="toggle-label">Workshop publications</span>
</div>
<div class="toggle-container">
  <label class="switch">
    <input type="checkbox" id="other-toggle">
    <span class="slider"></span>
  </label>
  <span class="toggle-label">Other publications</span>
</div>
<!--
<div class="toggle-container">
  <label class="switch">
    <input type="checkbox" id="superseded-toggle">
    <span class="slider"></span>
  </label>
  <span class="toggle-label">Superseded publications</span>
</div>
-->

{%- for y in page.years %}
  <h2 class="year">{{ y }}</h2>
  <div class="conference-on" style="display: none;">
    {% bibliography -f papers_conference -q @*[year={{ y }}]* %}
  </div>
    <div class="journal-on" style="display: none;">
    {% bibliography -f papers_journal -q @*[year={{ y }}]* %}
  </div>
  <div class="workshop-on" style="display: none;">
    {% bibliography -f papers_workshop -q @*[year={{ y }}]* %}
  </div>
  <div class="other-on" style="display: none;">
    {% bibliography -f papers_other -q @*[year={{ y }}]* %}
  </div>
  <!--
  <div class="superseded-on" style="display: none;">
    {% bibliography -f papers_superseded -q @*[year={{ y }}]* %}
  </div>
  -->
{% endfor %}

<script>
  function initializeToggle(toggleId, contentOnClass) {
    const toggle = document.getElementById(toggleId);
    const contentOnElements = document.querySelectorAll("." + contentOnClass);

    // Set initial display state based on the toggle's checked state
    contentOnElements.forEach(el => el.style.display = toggle.checked ? "block" : "none");

    // Add event listener to handle toggle change
    toggle.addEventListener("change", () => {
      contentOnElements.forEach(el => el.style.display = toggle.checked ? "block" : "none");
    });
  }

  function initializeAllToggles() {
    initializeToggle("conference-toggle", "conference-on");
    initializeToggle("journal-toggle", "journal-on");
    initializeToggle("workshop-toggle", "workshop-on");
    initializeToggle("other-toggle", "other-on");
    // initializeToggle("superseded-toggle", "superseded-on");
  }

  document.addEventListener("DOMContentLoaded", function () {
    initializeAllToggles()
  });

  window.addEventListener("pageshow", function () {
    initializeAllToggles()
  });
</script>

</div>