---
layout: home
title: Home
---

# ⚡ Welcome to Pokevew

Scroll through posts 👇

---

{% for post in site.posts %}

<details>
  <summary><strong>{{ post.title }}</strong> — {{ post.date | date: "%B %d, %Y" }}</summary>

  <div style="margin-top: 10px;">
    {{ post.content }}
  </div>

</details>

<br>

{% endfor %}
