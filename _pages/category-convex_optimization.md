---
title: "Convex Optimization"
layout: archive
permalink: /convex_optimization/
author_profile: false
sidebar_main: true
sidebar:
    nav: "docs"
---

{% assign posts = site.categories.convex_optimization %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}