---
title: "Regularization Method"
layout: archive
classes: wide <!-- 본문 늘리기!!!-->
permalink: categories/Regularization
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.Regularization %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}