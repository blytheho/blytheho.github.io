---
layout: page
title: Research
permalink: /research/
position: 2
---

<style>
/* ── Entry card ─────────────────────────────────────── */
.rlist-entry {
  display: grid;
  grid-template-columns: 300px minmax(0, 1fr);
  gap: 2rem;
  padding: 1.5rem 0.5rem;
  border-top: 1px solid #e0e0e0;
  position: relative;
  align-items: center;
}

/* ── Thumbnail box (left column): fixed 3:2 frame, image letterboxed ── */
.rlist-img-col {
  position: relative;
  width: 100%;
  aspect-ratio: 3 / 2;
  box-sizing: border-box;
  background: #fff;
  border: 1px solid #e8e8e8;
  border-radius: 6px;
  overflow: hidden;
}
.rlist-img-col.rlist-img-empty {
  background: none;
  border: none;
}
/* Override theme's global img rule (padding: 0 9%) so contain uses the full frame */
.rlist-img-col img.rlist-imgbox {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  max-width: none;
  margin: 0;
  padding: 8px;
  box-sizing: border-box;
  border-radius: 0;
  object-fit: contain;
  object-position: center;
  display: block;
}
.rlist-imgplaceholder {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.72em;
  color: #bbb;
  text-align: center;
  line-height: 1.4;
  border: 1px dashed #ccc;
  border-radius: 6px;
  background: #f8f8f8;
}

/* ── Content column (right) ────────────────────────── */
.rlist-body { min-width: 0; }
.rlist-meta-row {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  flex-wrap: wrap;
  margin-bottom: 0.45rem;
}
.rlist-venue {
  font-size: 0.8em;
  color: #666;
  line-height: 1.4;
}
.rlist-badge {
  display: inline-block;
  background: #1a3a4a;
  color: #fff;
  font-size: 0.7em;
  font-weight: 700;
  padding: 3px 8px;
  border-radius: 3px;
  text-transform: uppercase;
  letter-spacing: 0.03em;
}
.rlist-title { margin: 0 0 0.4rem; font-size: 1.05em; line-height: 1.35; }
.rlist-title a { color: inherit; text-decoration: none; }
.rlist-authors { margin: 0 0 0.5rem; font-size: 0.85em; color: #888; }
.rlist-authors b { color: #444; }
.rlist-authnote { font-size: 0.9em; color: #aaa; }
.rlist-excerpt { margin: 0; color: #555; font-size: 0.9em; line-height: 1.55; }
.rlist-note { font-size: 0.8em; color: #888; margin: 0.4rem 0 0; font-style: italic; }
.rlist-linkrow {
  margin: 0.6rem 0 0;
  display: inline-flex;
  align-items: baseline;
  flex-wrap: wrap;
  gap: 1rem;
  position: relative;
  z-index: 2;
}
.rlist-linkrow a {
  font-size: 0.82em;
  color: #1a3a4a;
  text-decoration: none;
  font-weight: 600;
}
.rlist-linkrow a:hover { text-decoration: underline; }

/* ── Clickable card (entries with a detail page) ───────
   The title link is stretched over the whole card, so the
   card is clickable and screen readers still get one real link. */
.rlist-lead { border-radius: 4px; transition: background 0.15s; }
.rlist-lead:hover { background: rgba(26,58,74,0.04); }
.rlist-lead:hover .rlist-title a { text-decoration: underline; }
/* Theme sets `article a:hover { filter: ... }`; a filter makes the link the
   containing block of its ::after, shrinking the overlay on hover. */
.rlist-lead .rlist-title a,
.rlist-lead .rlist-title a:hover { filter: none; }
.rlist-lead .rlist-title a::after {
  content: "";
  position: absolute;
  inset: 0;
  z-index: 1;
  border-radius: 4px;
}
.rlist-lead .rlist-title a:focus-visible { outline: none; }
.rlist-lead .rlist-title a:focus-visible::after { outline: 2px solid #1a3a4a; outline-offset: 2px; }


/* ── Compact desktop/laptop layout (>= 768px): wide, short cards ── */
@media (min-width: 768px) {
  .rlist-entry {
    grid-template-columns: 216px minmax(0, 1fr);
    gap: 1.25rem;
    padding: 0.65rem 0.5rem;
  }
  .rlist-meta-row { margin-bottom: 0.15rem; }
  .rlist-title { font-size: 1em; margin-bottom: 0.2rem; }
  .rlist-authors { margin-bottom: 0.2rem; font-size: 0.82em; }
  .rlist-excerpt { font-size: 0.84em; line-height: 1.4; }
  .rlist-entry:not(.rlist-ext):not(.rlist-full) .rlist-excerpt {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  .rlist-note { margin-top: 0.25rem; font-size: 0.78em; }
  .rlist-linkrow { margin-top: 0.35rem; }
}

/* Wide laptop screens (>= 1100px): widen the list and move the link row up beside
   the venue/badge row, which saves a line per card. */
@media (min-width: 1100px) {
  .rlist-wrap { margin-left: -4rem; margin-right: -4rem; }
  /* Grid, not absolute positioning: a positioned .rlist-body would shrink the
     clickable-card overlay to the text column and leave the thumbnail dead. */
  .rlist-body { display: grid; grid-template-columns: minmax(0, 1fr) auto; column-gap: 1rem; align-content: start; }
  .rlist-body > * { grid-column: 1 / -1; }
  .rlist-body > .rlist-meta-row { grid-column: 1; grid-row: 1; }
  .rlist-body > .rlist-linkrow { grid-column: 2; grid-row: 1; margin: 0; gap: 0.9rem; align-self: center; }
}

/* ── Mobile (< 768px) ───────────────────────────────── */
@media (max-width: 767.98px) {
  .rlist-entry {
    grid-template-columns: minmax(0, 1fr);
    gap: 0.75rem;
    padding: 1rem 0.25rem;
  }
  .rlist-img-col { width: 100%; }
  .rlist-img-col.rlist-img-empty { display: none; }
}
</style>

<div class="rlist-wrap">

{% comment %} Posts plus card-only entries (_research_cards, no detail page), in the manual `order` set in each entry's front matter. {% endcomment %}
{% assign entries = site.posts | concat: site.research_cards | sort: "order" %}
{% for post in entries %}
{% assign vparts = post.venue_display | split: " · " %}
{% assign thumb = post.card_image | default: post.thumbnail | strip %}
{% if post.has_detail %}{% assign card_href = post.url | relative_url %}{% elsif post.external_url %}{% assign card_href = post.external_url %}{% elsif post.links.poster %}{% assign card_href = post.links.poster | relative_url %}{% else %}{% assign card_href = "" %}{% endif %}

<div class="rlist-entry{% if card_href != "" %} rlist-lead{% endif %}{% if post.external_url %} rlist-ext{% endif %}{% if post.full_excerpt %} rlist-full{% endif %}">
  <div class="rlist-img-col{% if thumb == "" and jekyll.environment != "development" %} rlist-img-empty{% endif %}">
    {% if thumb != "" %}<img src="{{ thumb | relative_url }}" alt="{{ post.card_alt }}" class="rlist-imgbox" loading="lazy" />{% elsif jekyll.environment == "development" %}<div class="rlist-imgplaceholder">Image<br>placeholder</div>{% endif %}
  </div>
  <div class="rlist-body">
    <div class="rlist-meta-row">
      {% if post.venue_display %}<span class="rlist-venue">{% if vparts.size == 2 and vparts[1].size < 12 %}{{ vparts[0] }}&nbsp;<span style="white-space:nowrap">· {{ vparts[1] }}</span>{% else %}{{ post.venue_display }}{% endif %}</span>{% endif %}
      {% if post.pub_type %}<span class="rlist-badge">{{ post.pub_type }}</span>{% endif %}
    </div>
    <h3 class="rlist-title">{% if card_href != "" %}<a href="{{ card_href }}"{% unless post.has_detail %} target="_blank" rel="noopener noreferrer"{% endunless %}>{{ post.title }}</a>{% else %}{{ post.title }}{% endif %}</h3>
    {% if post.authors %}<p class="rlist-authors">{{ post.authors }}{% if post.authors_note %} <span class="rlist-authnote">{{ post.authors_note }}</span>{% endif %}</p>{% endif %}
    <p class="rlist-excerpt">{{ post.excerpt | strip_html }}</p>
    {% if post.contribution_note %}<p class="rlist-note">{{ post.contribution_note }}</p>{% endif %}
    {% if post.has_detail or post.links or post.external_url %}
    <div class="rlist-linkrow">
      {% if post.has_detail %}<a href="{{ post.url | relative_url }}" tabindex="-1">Details →</a>{% endif %}
      {% if post.external_url %}<a href="{{ post.external_url }}" tabindex="-1" target="_blank" rel="noopener noreferrer">Paper ↗</a>{% endif %}
      {% if post.links.paper %}<a href="{{ post.links.paper }}" target="_blank" rel="noopener">Paper ↗</a>{% endif %}
      {% if post.links.doi %}<a href="{{ post.links.doi }}" target="_blank" rel="noopener">DOI ↗</a>{% endif %}
      {% if post.links.poster %}<a href="{{ post.links.poster | relative_url }}" target="_blank" rel="noopener">Poster ↗</a>{% endif %}
      {% if post.links.slides %}<a href="{{ post.links.slides }}" target="_blank" rel="noopener">Slides ↗</a>{% endif %}
      {% if post.links.code %}<a href="{{ post.links.code }}" target="_blank" rel="noopener">Code ↗</a>{% endif %}
    </div>
    {% endif %}
  </div>
</div>

{% endfor %}


</div>
