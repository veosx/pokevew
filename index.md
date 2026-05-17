---
layout: default
title: Home
---

<style>
  :root {
    --pv-bg: #f3fbf8;
    --pv-surface: rgba(255, 255, 255, .84);
    --pv-surface-soft: rgba(221, 246, 237, .78);
    --pv-ink: #17212b;
    --pv-muted: #617080;
    --pv-line: #dbe3ea;
    --pv-brand: #1f8f75;
    --pv-brand-dark: #126452;
    --pv-accent: #ffcb47;
    --pv-blue: #2c86ff;
    --pv-cyan: #20d8ff;
    --pv-radius: 8px;
  }

  body.pv-dark {
    --pv-bg: #071018;
    --pv-surface: rgba(15, 28, 39, .86);
    --pv-surface-soft: rgba(38, 72, 84, .72);
    --pv-ink: #eef8ff;
    --pv-muted: #a9bdc9;
    --pv-line: rgba(170, 210, 225, .18);
    --pv-brand: #45d4bd;
    --pv-brand-dark: #8af4df;
    color-scheme: dark;
  }

  body {
    background:
      radial-gradient(circle at top left, rgba(31, 143, 117, .16), transparent 34rem),
      radial-gradient(circle at top right, rgba(255, 203, 71, .16), transparent 28rem),
      linear-gradient(180deg, #fbfffd 0%, var(--pv-bg) 34rem);
  }

  .pv-wrap {
    max-width: 1180px;
    margin: 0 auto;
    color: var(--pv-ink);
    font-family: Inter, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  }

  .pv-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
    padding: 18px 0 14px;
  }

  .pv-brand {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .pv-ball {
    width: 42px;
    height: 42px;
    border-radius: 50%;
    display: grid;
    place-items: center;
    background: linear-gradient(180deg, #e94141 0 47%, #1d252d 47% 53%, #fff 53% 100%);
    border: 2px solid #1d252d;
    box-shadow: 0 8px 24px rgba(233, 65, 65, .22);
    position: relative;
    overflow: hidden;
  }

  .pv-ball:before {
    content: "";
    position: absolute;
    inset: 18px 0 auto;
    height: 6px;
    background: #1d252d;
  }

  .pv-ball:after {
    content: "";
    width: 16px;
    height: 16px;
    border: 4px solid #1d252d;
    border-radius: 50%;
    background: #fff;
    z-index: 1;
  }

  .pv-title {
    margin: 0;
    font-size: clamp(1.45rem, 4vw, 2.1rem);
    line-height: 1;
    font-weight: 800;
    letter-spacing: 0;
  }

  .pv-subtitle {
    margin: 4px 0 0;
    color: var(--pv-muted);
    font-size: .84rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: .08em;
  }

  .pv-theme {
    min-width: 86px;
    height: 42px;
    border: 1px solid var(--pv-line);
    border-radius: 999px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 7px;
    padding: 0 13px;
    background: var(--pv-surface);
    color: var(--pv-ink);
    font-size: .86rem;
    font-weight: 800;
    cursor: pointer;
  }

  .pv-theme:before {
    content: "";
    width: 11px;
    height: 11px;
    border-radius: 50%;
    background: var(--pv-blue);
    box-shadow: 0 0 16px rgba(44, 134, 255, .85);
  }

  .pv-ticker {
    min-height: 46px;
    display: flex;
    align-items: center;
    gap: 14px;
    margin: 0 0 24px;
    padding: 0 16px;
    border: 1px solid var(--pv-line);
    border-radius: var(--pv-radius);
    background: rgba(248, 255, 252, .72);
    color: var(--pv-muted);
    font-size: .92rem;
    font-weight: 700;
    overflow: hidden;
  }

  .pv-ticker strong {
    flex: 0 0 auto;
    color: var(--pv-ink);
  }

  .pv-ticker a {
    color: var(--pv-brand-dark);
    font-weight: 800;
    text-decoration: none;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .pv-grid {
    display: grid;
    grid-template-columns: minmax(0, 1fr) 320px;
    gap: 30px;
    align-items: start;
  }

  .pv-feed {
    display: grid;
    gap: 18px;
  }

  .pv-card {
    background:
      linear-gradient(var(--pv-surface), var(--pv-surface)) padding-box,
      linear-gradient(135deg, rgba(44, 134, 255, .95), rgba(32, 216, 255, .64), rgba(138, 244, 223, .7), rgba(255, 255, 255, .72)) border-box;
    border: 1px solid transparent;
    border-radius: var(--pv-radius);
    box-shadow: 0 16px 42px rgba(44, 134, 255, .14), 0 12px 34px rgba(24, 36, 51, .06);
    overflow: hidden;
  }

  .pv-card-header {
    padding: 22px 24px 8px;
  }

  .pv-card-header:before {
    content: "";
    display: block;
    height: 5px;
    margin: -22px -24px 20px;
    background: linear-gradient(90deg, var(--pv-blue), var(--pv-cyan), var(--pv-brand), var(--pv-accent));
  }

  .pv-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 14px;
  }

  .pv-tag {
    display: inline-flex;
    align-items: center;
    min-height: 28px;
    padding: 0 10px;
    border-radius: 999px;
    background: linear-gradient(135deg, rgba(44, 134, 255, .96), rgba(32, 216, 255, .76));
    color: #fff;
    box-shadow: 0 8px 18px rgba(44, 134, 255, .2);
    font-size: .74rem;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: .08em;
  }

  .pv-post-title {
    margin: 0;
    font-size: clamp(1.42rem, 3vw, 2.2rem);
    line-height: 1.13;
    font-weight: 800;
    letter-spacing: 0;
  }

  .pv-post-title a {
    color: var(--pv-ink);
    text-decoration: none;
  }

  .pv-meta {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 8px 14px;
    margin-top: 12px;
    color: var(--pv-muted);
    font-size: .86rem;
    font-weight: 700;
  }

  .pv-content {
    padding: 8px 24px 24px;
    color: var(--pv-ink);
    font-size: 1rem;
    line-height: 1.75;
  }

  .pv-content img {
    border-radius: var(--pv-radius);
    margin: 18px auto;
  }

  .pv-read-link {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-height: 40px;
    margin-top: 12px;
    padding: 0 15px;
    border: 1px solid var(--pv-line);
    border-radius: 999px;
    background: var(--pv-surface);
    color: var(--pv-brand-dark);
    font-size: .9rem;
    font-weight: 800;
    text-decoration: none;
  }

  .pv-side {
    position: sticky;
    top: 18px;
    display: grid;
    gap: 18px;
  }

  .pv-widget {
    padding: 20px;
    border: 1px solid var(--pv-line);
    border-radius: var(--pv-radius);
    background: var(--pv-surface);
    box-shadow: 0 12px 28px rgba(24, 36, 51, .05);
  }

  .pv-chip {
    display: inline-flex;
    align-items: center;
    min-height: 24px;
    margin-bottom: 10px;
    padding: 0 9px;
    border-radius: 999px;
    background: linear-gradient(135deg, rgba(44, 134, 255, .96), rgba(32, 216, 255, .72));
    color: #fff;
    font-size: .68rem;
    font-weight: 800;
    letter-spacing: .08em;
    text-transform: uppercase;
  }

  .pv-widget h2 {
    margin: 0;
    color: var(--pv-ink);
    font-size: 1.22rem;
    line-height: 1.15;
    font-weight: 800;
  }

  .pv-widget p, .pv-widget li {
    color: var(--pv-muted);
    font-size: .94rem;
    font-weight: 600;
    line-height: 1.55;
  }

  .pv-widget ul {
    margin: 10px 0 0;
    padding-left: 1.1rem;
  }

  @media (max-width: 900px) {
    .pv-header { align-items: flex-start; flex-direction: column; }
    .pv-grid { grid-template-columns: 1fr; }
    .pv-side { position: static; }
  }

  @media (max-width: 640px) {
    .pv-card-header, .pv-content { padding-left: 16px; padding-right: 16px; }
    .pv-card-header:before { margin-left: -16px; margin-right: -16px; }
  }
</style>

<div class="pv-wrap">
  <header class="pv-header">
    <div class="pv-brand">
      <span class="pv-ball" aria-hidden="true"></span>
      <div>
        <h1 class="pv-title">Pokevew</h1>
        <p class="pv-subtitle">Pokemon news and updates</p>
      </div>
    </div>
    <button class="pv-theme" id="pv-theme" type="button">Dark</button>
  </header>

  <div class="pv-ticker">
    <strong>Latest updates</strong>
    {% assign latest_post = site.posts | first %}
    {% if latest_post %}
      <a id="pv-ticker-link" href="{{ latest_post.url | relative_url }}">{{ latest_post.title }}</a>
    {% else %}
      <a id="pv-ticker-link" href="{{ "/" | relative_url }}">New posts will appear here</a>
    {% endif %}
  </div>

  <div class="pv-grid">
    <main class="pv-feed" aria-label="Latest Pokevew news">
      {% if site.posts.size == 0 %}
      <article class="pv-card">
        <header class="pv-card-header">
          <div class="pv-tags"><span class="pv-tag">News</span></div>
          <h2 class="pv-post-title">Your first Pokevew story goes here</h2>
          <div class="pv-meta"><span>Create a file in _posts to publish it.</span></div>
        </header>
        <div class="pv-content">
          <p>Once you add a Markdown post, it will appear here automatically with the same frosted news-card design.</p>
        </div>
      </article>
      {% endif %}

      {% for post in site.posts %}
      <article class="pv-card">
        <header class="pv-card-header">
          <div class="pv-tags">
            {% if post.categories.size > 0 %}
              {% for label in post.categories limit: 4 %}
                <span class="pv-tag">{{ label }}</span>
              {% endfor %}
            {% elsif post.tags.size > 0 %}
              {% for label in post.tags limit: 4 %}
                <span class="pv-tag">{{ label }}</span>
              {% endfor %}
            {% else %}
              <span class="pv-tag">News</span>
            {% endif %}
          </div>
          <h2 class="pv-post-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h2>
          <div class="pv-meta">
            <span>{{ post.date | date: "%B %d, %Y" }}</span>
            {% if post.update_of %}
              <a href="{{ post.update_of | relative_url }}">Update to earlier story</a>
            {% endif %}
          </div>
        </header>

        <div class="pv-content">
          {% if forloop.first %}
            {{ post.content }}
          {% else %}
            {{ post.excerpt }}
            <a class="pv-read-link" href="{{ post.url | relative_url }}">Read full story</a>
          {% endif %}
        </div>
      </article>
      {% endfor %}
    </main>

    <aside class="pv-side" aria-label="Pokevew widgets">
      <section class="pv-widget">
        <span class="pv-chip">Pokemon of the day</span>
        <h2 id="pv-pokemon-name">Pikachu</h2>
        <p id="pv-pokemon-copy">A quick daily spotlight before readers dive back into the news.</p>
      </section>

      <section class="pv-widget">
        <span class="pv-chip">Card of the day</span>
        <h2 id="pv-card-name">Base Set Charizard</h2>
        <p id="pv-card-copy">A collector icon and a natural TCG conversation starter.</p>
      </section>

      <section class="pv-widget">
        <span class="pv-chip">Anime fact</span>
        <h2 id="pv-anime-name">Ash and Pikachu</h2>
        <p id="pv-anime-copy">Their first episode bond still shapes how fans read later callbacks.</p>
      </section>

      <section class="pv-widget">
        <span class="pv-chip">Post guide</span>
        <h2>New story format</h2>
        <p>Create files in <code>_posts</code> named <code>YYYY-MM-DD-title.md</code>. Use categories like <code>News</code>, <code>Update</code>, <code>TCG</code>, <code>VG</code>, or <code>Anime</code>.</p>
      </section>
    </aside>
  </div>
</div>

<script>
  window.PV_POSTS = [
    {% for post in site.posts limit: 8 %}
      {
        title: {{ post.title | jsonify }},
        url: {{ post.url | relative_url | jsonify }}
      }{% unless forloop.last %},{% endunless %}
    {% endfor %}
  ];

  (function () {
    var themeButton = document.getElementById("pv-theme");
    var savedTheme = localStorage.getItem("pokevew-theme");
    if (savedTheme === "dark") document.body.classList.add("pv-dark");

    function syncThemeLabel() {
      if (themeButton) themeButton.textContent = document.body.classList.contains("pv-dark") ? "Light" : "Dark";
    }

    if (themeButton) {
      themeButton.addEventListener("click", function () {
        document.body.classList.toggle("pv-dark");
        localStorage.setItem("pokevew-theme", document.body.classList.contains("pv-dark") ? "dark" : "light");
        syncThemeLabel();
      });
      syncThemeLabel();
    }

    var ticker = document.getElementById("pv-ticker-link");
    var posts = window.PV_POSTS || [];
    var index = 0;
    if (ticker && posts.length > 1) {
      window.setInterval(function () {
        index = (index + 1) % posts.length;
        ticker.href = posts[index].url;
        ticker.textContent = posts[index].title;
      }, 5200);
    }

    var dayIndex = Math.floor(Date.now() / 86400000);
    var pokemon = [
      ["Pikachu", "Known for its electric spark and mascot status, Pikachu is a perfect daily warm-up for quick Pokemon news readers."],
      ["Eevee", "Eevee connects naturally to games, anime, and collecting because of its many evolutions."],
      ["Lucario", "Lucario is a fan favorite thanks to aura-focused lore, strong game appearances, and memorable anime moments."],
      ["Gengar", "A playful Ghost-type spotlight that fits rumors, spooky events, and late-night update posts."],
      ["Greninja", "Greninja brings a fast, competitive feel and remains one of the most recognizable modern starters."]
    ];
    var cards = [
      ["Base Set Charizard", "A collector icon and an easy reference point whenever TCG excitement starts heating up."],
      ["Pikachu Illustrator", "One of the hobby's most famous prize cards, useful for quick collector context."],
      ["Moonbreon", "A modern chase-card example that still gets people talking in TCG circles."],
      ["Ancient Mew", "A nostalgic movie-era card that fits anime and TCG crossover stories."],
      ["Mewtwo GX", "A strong spotlight for readers who like card art, power cards, and classic Legendary Pokemon."]
    ];
    var facts = [
      ["Ash and Pikachu", "Their first episode bond still shapes how fans read many later anime callbacks."],
      ["Team Rocket", "The recurring motto became one of the anime's most recognizable running bits."],
      ["Pokemon Contests", "Contest arcs helped the anime spotlight style, performance, and partner chemistry."],
      ["Regional companions", "Each region reshuffles the cast so the anime can reset tone without losing continuity."],
      ["Movie mythicals", "The films often gave Mythical Pokemon their biggest personality moments before games expanded them."]
    ];

    function fillDaily(nameId, copyId, list) {
      var item = list[dayIndex % list.length];
      var name = document.getElementById(nameId);
      var copy = document.getElementById(copyId);
      if (name && copy) {
        name.textContent = item[0];
        copy.textContent = item[1];
      }
    }

    fillDaily("pv-pokemon-name", "pv-pokemon-copy", pokemon);
    fillDaily("pv-card-name", "pv-card-copy", cards);
    fillDaily("pv-anime-name", "pv-anime-copy", facts);
  }());
</script>
