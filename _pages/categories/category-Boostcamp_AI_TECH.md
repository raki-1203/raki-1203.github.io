---
title: "Boostcamp_AI_TECH"
layout: archive
classes: wide <!-- 본문 늘리기!!!-->
permalink: categories/Boostcamp_AI_TECH
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.Boostcamp_AI_TECH %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}