---
layout: post
title: Day's tool
date: 2019-10-13 00:00
---

<li><time>{{ post.date | date:"%d %b" }} - </time>
    <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
            {{ post.title }}
    </a>
</li>
