---
layout: blog_post
title: 'Snowflake Summit 2025'
date: 2025-06-05
tags:
  - San Francisco
  - Conference
---

## Unlocking Alpha: AI-Powered Earnings Call Analysis

This hands-on lab explores the integration of Snowflake Notebooks and Cortex AI with S&P Global Market Intelligence’s Machine-Readable Transcripts dataset to analyze executive communication duri[...]

## Official Website

<div style="width:100%;max-width:1100px;margin:0 auto;">
  <div style="position:relative;padding-bottom:75%;height:0;overflow:hidden;">
    <iframe id="snowflakesummit2025-pdf-frame" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" title="Snowflake Summit 2025 PDF"></iframe>
  </div>
  <p style="text-align:center;margin-top:0.5rem">
    <a href="{{ '/assets/images/etc/SessionCatalog2025.pdf' | relative_url }}">Open PDF in a new tab</a>
  </p>
</div>

<script>
  // encodeURI handles spaces/unsafe chars in the filename
  const pdfUrl = encodeURI('{{ "/assets/images/etc/SessionCatalog2025.pdf" | relative_url }}');
  document.getElementById('snowflakesummit2025-pdf-frame').src = pdfUrl;
</script>

## Pictures

<!-- Enhanced photo gallery: thumbnails, WebP fallback, lazy loading, pagination, and GLightbox for lightbox/gestures -->

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/glightbox/dist/css/glightbox.min.css">
<style>
.gallery-wrap { max-width:1100px; margin:1rem auto; }
.gallery { display:grid; grid-template-columns: repeat(auto-fill,minmax(200px,1fr)); gap:12px; }
.thumb { display:block; position:relative; overflow:hidden; border-radius:6px; box-shadow:0 2px 6px rgba(0,0,0,0.12); }
.thumb img { width:100%; height:200px; object-fit:cover; display:block; transition: transform .25s ease; }
.thumb:hover img { transform: scale(1.03); }
.caption { position:absolute; left:0; right:0; bottom:0; background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.55) 100%); color:#fff; padding:8px 10px; font-size:0.9rem; }
.hidden { display:none !important; }
@media (max-width:480px) { .thumb img { height:140px; } }
</style>

<div class="gallery-wrap">
  {% assign gallery_folder = 'assets/images/event_photos/SnowflakeSummit2025' %}

  {% comment %} Build list of original images (exclude thumbs/webp subfolders) {% endcomment %}
  {% assign photos = site.static_files | where_exp: "f", "f.path contains gallery_folder" %}
  {% assign photos = photos | sort: 'path' %}

  {% assign meta_map = site.data.photos.snowflakesummit2025 %}
  {% assign per_page = 12 %}

  {% if photos.size == 0 %}
    <p>No photos found in {{ gallery_folder }}. Add images and run the image generation script to create thumbnails and WebP versions (see /scripts/README.md).</p>
  {% else %}
    <div id="photo-gallery" class="gallery" aria-label="Snowflake Summit 2025 photos">
      {% for file in photos %}
        {% assign filename = file.path | split: '/' | last %}
        {% assign basename = filename | split: '.' | first %}
        {% comment %} Skip files from thumbs or webp folders if encountered {% endcomment %}
        {% if file.path contains '/thumbs/' or file.path contains '/webp/' %}
          {% continue %}
        {% endif %}

        {% assign meta = meta_map[basename] %}
        {% if meta == nil %}
          {% assign caption = basename | replace: '_', ' ' | replace: '-', ' ' | capitalize %}
          {% assign alt = caption %}
        {% else %}
          {% assign caption = meta.caption | default: basename %}
          {% assign alt = meta.alt | default: caption %}
        {% endif %}

        {% comment %} Paths for thumbnail and webp fallbacks. The image generation script will create 'thumbs' and 'webp' subfolders. {% endcomment %}
        {% assign thumb_path = gallery_folder | append: '/thumbs' %}
        {% assign thumb_src = thumb_path | append: '/' | append: filename %}
        {% assign thumb_webp = thumb_path | append: '/' | append: basename | append: '.webp' %}

        {% assign full_webp = gallery_folder | append: '/webp/' | append: basename | append: '.webp' %}

        <a href="{{ file.path | relative_url }}"
           class="thumb glightbox"
           data-gallery="snowflake2025"
           data-title="{{ caption }}"
           data-desc="{{ meta.description | default: '' }}"
           data-type="image"
           data-alt="{{ alt }}"
           data-full-webp="{{ full_webp | relative_url }}"
           data-full="{{ file.path | relative_url }}"
           data-index="{{ forloop.index0 }}"
           {% unless forloop.index0 < per_page %}data-hidden="true" style="display:none;"{% endunless %}>

          <picture>
            <source srcset="{{ thumb_webp | relative_url }}" type="image/webp">
            <img src="{{ thumb_src | relative_url }}" loading="lazy" alt="{{ alt }}">
          </picture>
          <div class="caption">{{ caption }}</div>
        </a>
      {% endfor %}
    </div>

    {% if photos.size > per_page %}
      <p style="text-align:center;margin-top:12px;">
        <button id="show-more" class="button">Show more</button>
      </p>
    {% endif %}

    <script src="https://cdn.jsdelivr.net/npm/glightbox/dist/js/glightbox.min.js"></script>

    <script>
      (function(){
        // Initialize GLightbox with lazy loading support
        var lightbox = GLightbox({
          selector: '.glightbox',
          touchNavigation: true,
          loop: false,
          openEffect: 'zoom'
        });

        // Replace lightbox src with WebP if available when opening (lazy load full-size)
        document.addEventListener('glightbox_open', function(e){
          var active = lightbox.getActiveSlide();
          if(!active) return;
          var node = active.node; // anchor
          if(!node) return;
          var fullWebp = node.getAttribute('data-full-webp');
          var full = node.getAttribute('data-full');
          if(fullWebp){
            active.setContent('<img src="' + fullWebp + '" loading="lazy" alt="' + (node.getAttribute('data-alt')||'') + '"/>');
          } else if(full){
            active.setContent('<img src="' + full + '" loading="lazy" alt="' + (node.getAttribute('data-alt')||'') + '"/>');
          }
        });

        // Pagination / Show more
        var perPage = {{ per_page }};
        var showMoreBtn = document.getElementById('show-more');
        if(showMoreBtn){
          var visible = perPage;
          showMoreBtn.addEventListener('click', function(){
            var nodes = document.querySelectorAll('#photo-gallery .thumb');
            var added = 0;
            for(var i=visible; i<Math.min(nodes.length, visible+perPage); i++){
              nodes[i].style.display = '';
              nodes[i].setAttribute('data-hidden','false');
              added++;
            }
            visible += added;
            if(visible >= nodes.length) showMoreBtn.style.display = 'none';
          });
        }
      })();
    </script>
  {% endif %}
</div>
