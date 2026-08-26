---
layout: blog_post
title: 'Snowflake Summit 2026'
date: 2026-06-02
tags:
  - San Francisco
  - Conference
---

## AI in Action: Real-World FSI Production Showcases

Leading financial institutions are already deploying AI to drive measurable ROI. This curated collection showcases the most impactful AI stories currently in production across the industry. Explore how your peers are moving from pilot to scale, leveraging the Snowflake AI Data Cloud to solve complex challenges in risk, customer experience and employee efficiency.

## Official Website

<div style="width:100%;max-width:1100px;margin:0 auto;">
  <div style="position:relative;padding-bottom:75%;height:0;overflow:hidden;">
    <iframe id="snowflakesummit2026-pdf-frame" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" title="Snowflake Summit 2026 PDF"></iframe>
  </div>
  <p style="text-align:center;margin-top:0.5rem">
    <a href="{{ '/assets/images/etc/SessionCatalog2026.pdf' | relative_url }}">Open PDF in a new tab</a>
  </p>
</div>

<script>
  // encodeURI handles spaces/unsafe chars in the filename
  const pdfUrl = encodeURI('{{ "/assets/images/etc/SessionCatalog2026.pdf" | relative_url }}');
  document.getElementById('snowflakesummit2026-pdf-frame').src = pdfUrl;
</script>

## Photo Gallery

<!-- Photo gallery: responsive grid with lightbox. Uses Jekyll's site.static_files to enumerate images in the folder assets/images/event_photos/SnowflakeSummit2026 -->

<style>
.photo-gallery-wrap { max-width:1100px; margin:1rem auto; }
.photo-gallery { display:grid; grid-template-columns: repeat(auto-fill,minmax(200px,1fr)); gap:12px; }
.photo-thumb { display:block; position:relative; overflow:hidden; border-radius:6px; box-shadow:0 2px 6px rgba(0,0,0,0.12); }
.photo-thumb img { width:100%; height:200px; object-fit:cover; display:block; transition: transform .25s ease; }
.photo-thumb:hover img { transform: scale(1.03); }
.photo-caption { position:absolute; left:0; right:0; bottom:0; background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.55) 100%); color:#fff; padding:8px 10px; font-size:0.9rem; }

/* Lightbox */
.lightbox-overlay { position:fixed; inset:0; background:rgba(0,0,0,0.85); display:flex; align-items:center; justify-content:center; z-index:2000; padding:20px; visibility:hidden; opacity:0; transition:opacity .2s ease; }
.lightbox-overlay.open { visibility:visible; opacity:1; }
.lightbox-content { max-width:95%; max-height:95%; }
.lightbox-content img { width:auto; height:auto; max-width:100%; max-height:80vh; display:block; margin:0 auto; border-radius:6px; }
.lightbox-close { position:absolute; top:18px; right:20px; background:transparent; border:0; color:#fff; font-size:1.6rem; cursor:pointer; }
.lightbox-caption { color:#ddd; text-align:center; margin-top:10px; font-size:0.95rem; }

@media (max-width:480px) {
  .photo-thumb img { height:140px; }
}
</style>
