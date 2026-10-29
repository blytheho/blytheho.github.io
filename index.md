---
layout: page
title: About
hide_title: true
---

<style>
/* ---- Colours: light blue cards, blue accent; both adapt to dark mode ---- */
:root {
  --accent: #3d5a9e;
  --on-accent: #fff;
  --card-bg: #eef2f9;
  --line: rgba(61, 90, 158, 0.16);
  --muted: #6f7b96;
}
html[data-theme="dark"] {
  --accent: #9db4ee; --on-accent: #14202b; --card-bg: #2a313d; --line: rgba(157, 180, 238, 0.2); --muted: #98a3bd;
}
@media (prefers-color-scheme: dark) {
  html:not([data-theme="light"]) {
    --accent: #9db4ee; --on-accent: #14202b; --card-bg: #2a313d; --line: rgba(157, 180, 238, 0.2); --muted: #98a3bd;
  }
}

/* ---- Type scale used on the whole page: 18px text, 15.5px details, 14.5px dates ---- */

/* Header */
.ha { display: grid; grid-template-columns: minmax(0, 1fr) 250px; gap: 2.5rem; align-items: center; margin: 0.5rem 0 2.2rem; }
.ha-eyebrow { margin: 0 0 0.4rem; font-size: 13px; font-weight: 700; letter-spacing: 0.09em; text-transform: uppercase; color: var(--accent); }
.ha h1 { margin: 0; font-size: 2.45rem; line-height: 1.15; }
.ha h1 span { font-weight: 400; color: var(--muted); font-size: 0.78em; margin-left: 0.35rem; }
.ha-pron { margin: 0.3rem 0 0; font-size: 15.5px; color: var(--muted); }
.ha-bio { margin: 1rem 0 0.7rem; font-size: 18px; line-height: 1.65; text-align: left; }
.ha-bio a { color: var(--accent); }
.ha-dept { margin: 0 0 1.1rem; font-size: 15.5px; color: var(--muted); display: flex; align-items: center; gap: 0.6rem; }
.ha-dept i { width: 1.1em; text-align: center; color: var(--accent); flex-shrink: 0; }
.ha-btns { display: flex; flex-wrap: wrap; gap: 0.5rem; }
.ha-btns a { display: inline-block; padding: 0.35rem 0.95rem; border: 1px solid var(--line); border-radius: 999px; font-size: 15px; font-weight: 600; text-decoration: none; color: var(--accent); background: var(--card-bg); }
.ha-btns a.primary { background: var(--accent); border-color: var(--accent); color: var(--on-accent); }
.ha-btns a:hover { filter: none; background: var(--accent); border-color: var(--accent); color: var(--on-accent); text-decoration: none; }
.ha img { width: 100%; aspect-ratio: 4 / 5; object-fit: cover; object-position: 50% 20%; border-radius: 16px; box-shadow: 0 10px 28px rgba(61, 90, 158, 0.22); padding: 0; margin: 0; max-width: none; display: block; }
@media (max-width: 700px) {
  .ha { grid-template-columns: 1fr; gap: 1.4rem; text-align: center; }
  .ha-photo { order: -1; width: 200px; margin: 0 auto; }
  .ha h1 { font-size: 2.05rem; }
  .ha-bio { text-align: center; }
  .ha-btns { justify-content: center; }
  .ha-dept { justify-content: center; text-align: left; }
}
</style>

<section class="ha">
  <div>
    <p class="ha-eyebrow">Research Assistant · Transportation Systems</p>
    <h1>Qijie (Jacquie) He <span>何绮婕</span></h1>
    <p class="ha-pron">Pronounced <em>chee-jyeh huh</em>, but please just call me Jacquie :)</p>
    <p class="ha-bio">Hi there! I'm Jacquie, a research assistant at Monash University working with <a href="https://scholar.google.com/citations?hl=en&user=28YF4pAAAAAJ&view_op=list_works&sortby=pubdate">Dr. Zhuo Chen</a>. Before that, I completed my master's degrees at Southeast University and Monash University under the supervision of <a href="https://scholar.google.com/citations?user=EzCLa-4AAAAJ&hl=en">Prof. Ziyuan Pu</a>.</p>
    <p class="ha-dept"><i class="fas fa-university" aria-hidden="true"></i><span>Department of Civil and Environmental Engineering, Monash University</span></p>
    <div class="ha-btns">
      <a class="primary" href="https://scholar.google.com/citations?user=Lcz4mq0AAAAJ&hl=en&oi=ao">Google Scholar</a>
      <a href="mailto:qijie.he@monash.edu">Email</a>
      <a href="https://github.com/blytheho">GitHub</a>
      <a href="https://www.linkedin.com/in/qijie-he/">LinkedIn</a>
    </div>
  </div>
  <div class="ha-photo"><img src="{{ '/assets/img/profile.jpg' | relative_url }}" alt="Qijie (Jacquie) He" /></div>
</section>

<style>
/* Sections: no box, a thin line above each one and a small uppercase blue heading.
   Only News sits in a light blue block. */
.card { margin: 0 0 1.9rem; }
.card:not(.card-filled) { border-top: 1px solid var(--line); padding-top: 1.6rem; }
.card-filled { border-radius: 18px; padding: 1.7rem 2rem 1.8rem; background: var(--card-bg); }
.card h2 {
  margin: 0 0 1rem;
  font-size: 1rem;
  line-height: 1.3;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--accent);
}
.card > p { font-size: 18px; line-height: 1.7; margin: 0 0 0.85rem; text-align: justify; hyphens: auto; -webkit-hyphens: auto; }
.card > p:last-child, .card > ul:last-child { margin-bottom: 0; }
.card a { color: var(--accent); }

/* News */
.news-list { list-style: none; padding: 0; margin: 0 0 0.4rem; }
.news-list li { display: grid; grid-template-columns: 8.5rem 1fr; gap: 1rem; padding: 0.55rem 0; border-bottom: 1px solid var(--line); font-size: 17px; line-height: 1.55; }
.news-list li:last-child { border-bottom: none; }
.news-date { color: var(--muted); font-size: 14.5px; font-weight: 700; padding-top: 0.1rem; }

/* Education and Experience: one card each, org with icon */
.cv-card h2 { margin-bottom: 0.9rem; }
.cv-item { margin-bottom: 1.05rem; }
.cv-item:last-child { margin-bottom: 0; }
.cv-card p { margin: 0; text-align: left; line-height: 1.45; }
.cv-org { display: flex; gap: 0.6rem; align-items: baseline; font-size: 18px !important; margin-bottom: 0.2rem !important; }
.cv-org i { width: 1.15em; text-align: center; color: var(--accent); flex-shrink: 0; font-size: 0.9em; }
.cv-row { padding-left: 1.85rem; font-size: 15.5px !important; }
/* Degree / role and its dates on one line; the date wraps below if the line is too long */
.cv-main { display: flex; flex-wrap: wrap; align-items: baseline; column-gap: 0.75rem; margin-bottom: 0.1rem !important; }
.cv-date { color: var(--muted); font-size: 14.5px; white-space: nowrap; }
.cv-sub { opacity: 0.85; }
@media (max-width: 600px) {
  .news-list li { grid-template-columns: 1fr; gap: 0.1rem; }
  .card-filled { padding: 1.2rem 1.15rem 1.3rem; border-radius: 14px; }
}
</style>

<div class="card" markdown="1">


## What I work on

My projects span traffic safety, scenario generation, active transportation and health, and now EV charging infrastructure. They look different, but they share one question: **how do transportation systems affect people's safety, well-being, and everyday lives, and can we anticipate problems before they happen?** In crash analysis, that meant finding which road features drive risk. In scenario generation, it meant creating the situations where autonomous vehicles fail, so those weaknesses can be found and fixed. In active transportation and health, it meant examining how walking and cycling infrastructure relates to health outcomes. For EV charging, it means testing where stations should go before they are built, so that they serve drivers' needs rather than causing long detours or sitting empty.

I’ve always found that exploring a topic from zero to one is a rewarding way to keep my eyes open and my curiosity fed. Every project starts with a question, and watching it take shape and become something I can test and argue about is what I enjoy most. So I’d like to keep working across various topics and see how the techniques and methods I learn in one carry over to the next.

</div>

<div class="card cv-card">
  <h2>Education</h2>
  <div class="cv-item">
    <p class="cv-org"><i class="fas fa-university" aria-hidden="true"></i><span><strong>Southeast University</strong></span></p>
    <p class="cv-row cv-main"><span>M.Eng. in Transportation Engineering</span><span class="cv-date">September 2023 – June 2026</span></p>
  </div>
  <div class="cv-item">
    <p class="cv-org"><i class="fas fa-university" aria-hidden="true"></i><span><strong>Monash University</strong></span></p>
    <p class="cv-row cv-main"><span>M.S. in Transportation Systems (Joint Program with Southeast University)</span><span class="cv-date">September 2023 – June 2026</span></p>
  </div>
  <div class="cv-item">
    <p class="cv-org"><i class="fas fa-university" aria-hidden="true"></i><span><strong>Foshan University</strong></span></p>
    <p class="cv-row cv-main"><span>B.Eng. in Transportation Engineering</span><span class="cv-date">September 2016 – June 2020</span></p>
  </div>
</div>

<div class="card cv-card">
  <h2>Experience</h2>
  <div class="cv-item">
    <p class="cv-org"><i class="fas fa-university" aria-hidden="true"></i><span><strong>Monash University Suzhou</strong></span></p>
    <p class="cv-row cv-main"><span>Research Assistant</span><span class="cv-date">August 2026 – present</span></p>
    <p class="cv-row cv-sub"><span>Department of Civil and Environmental Engineering</span></p>
  </div>
  <div class="cv-item">
    <p class="cv-org"><i class="fas fa-building" aria-hidden="true"></i><span><strong><a href="https://www.sutpc.com/en/about.html">Shenzhen Urban Transport Planning Center</a></strong> (SUTPC)</span></p>
    <p class="cv-row cv-main"><span>Junior Engineer</span><span class="cv-date">June 2020 – May 2021</span></p>
    <p class="cv-row cv-sub"><span>City-level strategic transportation planning</span></p>
  </div>
</div>

<div class="card card-filled" markdown="1">

## News

<ul class="news-list">
  <li><span class="news-date">August 2026</span><span>Excited to join Monash University Suzhou as a research assistant!</span></li>
  <li><span class="news-date">July 2026</span><span>Graduated! I earned my master's degrees from Southeast University and Monash University.</span></li>
  <li><span class="news-date">June 2026</span><span>New paper alert 📢 My paper on using generative AI to augment crash data for crash frequency modeling is out in <em>Accident Analysis &amp; Prevention</em>! <a href="https://doi.org/10.1016/j.aap.2026.108508">[read more]</a></span></li>
  <li><span class="news-date">May 2026</span><span>New paper alert 📢 Our paper on safety-critical scenario generation for autonomous driving is now published in <em>Transportmetrica A: Transport Science</em>! <a href="https://doi.org/10.1080/23249935.2026.2666104">[read more]</a></span></li>
  <li><span class="news-date">January 2026</span><span>Back in DC! I presented my poster at TRB's 105th Annual Meeting. <a href="{{ '/news/' | relative_url }}">[read more]</a></span></li>
  <li><span class="news-date">January 2025</span><span>I presented my poster at the Transportation Research Board (TRB) 104th Annual Meeting! <a href="{{ '/news/' | relative_url }}">[read more]</a></span></li>
</ul>

<p style="margin-top: 0.8rem;"><a href="{{ '/news/' | relative_url }}">See all news &rarr;</a></p>

</div>
