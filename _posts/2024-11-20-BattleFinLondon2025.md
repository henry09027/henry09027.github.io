---
layout: blog_post
title: 'BattleFin London 2024'
date: 2024-11-20
tags:
  - London
  - Conference
---

## Generative AI Tools for Alpha Generation

In Earnings Calls, firms whose executives directly address analysts’ questions and remain on-topic outperform their off-topic peers, as focused communication enhances clarity and investor confidence.

Firms where analysts stick to the script in the executives' pre-prepared remarks on the earnings call outperform those where the analyst goes off-script. Off-script questions indicate the analyst is seeking additional information, leading to potential gaps in communication and transparency.

Firms where both executives remain on topic to the question asked and analysts remain on script outperform their off topic and off script peers.

## Official Website

<div style="width:100%;max-width:1100px;margin:0 auto;">
  <div style="position:relative;padding-bottom:75%;height:0;overflow:hidden;">
    <iframe id="BattleFin London 2025-pdf-frame" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" title="BattleFin London 2025 PDF"></iframe>
  </div>
  <p style="text-align:center;margin-top:0.5rem">
    <a href="{{ '/assets/images/etc/BattleFinLondonWebsite.pdf' | relative_url }}">Open PDF in a new tab</a>
  </p>
</div>

<script>
  // encodeURI handles spaces/unsafe chars in the filename
  const pdfUrl = encodeURI('{{ "/assets/images/etc/BattleFinLondonWebsite.pdf" | relative_url }}');
  document.getElementById('BattleFin London 2025-pdf-frame').src = pdfUrl;
</script>

## Photo Gallery

<style>
.photo-gallery-wrap {
  max-width: 1100px;
  margin: 1rem auto;
}

.photo-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 12px;
}

.photo-thumb {
  display: block;
  position: relative;
  overflow: hidden;
  border-radius: 6px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.12);
  cursor: pointer;
  background: #eee;
}

.photo-thumb img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  display: block;
  transition: transform 0.25s ease;
}

.photo-thumb:hover img {
  transform: scale(1.03);
}

.photo-caption {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0) 0%,
    rgba(0, 0, 0, 0.65) 100%
  );
  color: #fff;
  padding: 20px 10px 8px;
  font-size: 0.9rem;
}

/* =========================
   Lightbox
   ========================= */

.lightbox-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  padding: 20px;

  visibility: hidden;
  opacity: 0;
  transition: opacity 0.2s ease;
}

.lightbox-overlay.open {
  visibility: visible;
  opacity: 1;
}

.lightbox-content {
  max-width: 95vw;
  max-height: 95vh;
  text-align: center;
}

.lightbox-content img {
  width: auto;
  height: auto;
  max-width: 95vw;
  max-height: 80vh;
  display: block;
  margin: 0 auto;
  border-radius: 6px;
}

.lightbox-caption {
  color: #ddd;
  text-align: center;
  margin-top: 10px;
  font-size: 0.95rem;
}

.lightbox-close {
  position: absolute;
  top: 18px;
  right: 25px;

  background: transparent;
  border: 0;
  color: #fff;

  font-size: 2rem;
  line-height: 1;
  cursor: pointer;

  z-index: 10000;
}

.lightbox-close:hover {
  opacity: 0.7;
}

/* Previous / Next buttons */

.lightbox-prev,
.lightbox-next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);

  background: rgba(0, 0, 0, 0.4);
  border: none;
  color: white;

  font-size: 2rem;
  padding: 12px 18px;

  cursor: pointer;
  border-radius: 6px;
}

.lightbox-prev {
  left: 20px;
}

.lightbox-next {
  right: 20px;
}

.lightbox-prev:hover,
.lightbox-next:hover {
  background: rgba(0, 0, 0, 0.7);
}

/* Mobile */

@media (max-width: 480px) {
  .photo-gallery {
    grid-template-columns: repeat(2, 1fr);
    gap: 8px;
  }

  .photo-thumb img {
    height: 140px;
  }

  .lightbox-prev,
  .lightbox-next {
    font-size: 1.5rem;
    padding: 8px 12px;
  }

  .lightbox-prev {
    left: 8px;
  }

  .lightbox-next {
    right: 8px;
  }
}
</style>


<div class="photo-gallery-wrap">

  <div class="photo-gallery">

    {% assign photo_folder = "/assets/images/event_photos/BattleFinLondon2024" %}

    {% for file in site.static_files %}

      {% if file.path contains photo_folder %}

        {% assign extension = file.extname | downcase %}

        {% if extension == ".jpg"
           or extension == ".jpeg"
           or extension == ".png"
           or extension == ".webp"
           or extension == ".gif" %}

          {% assign filename = file.name
            | split: "."
            | first
            | replace: "_", " "
            | replace: "-", " "
          %}

          <div
            class="photo-thumb"
            data-full="{{ file.path }}"
            data-caption="{{ filename }}"
          >

            <img
              src="{{ file.path | relative_url }}"
              alt="{{ filename }}"
              loading="lazy"
            >

            <div class="photo-caption">
              {{ filename }}
            </div>

          </div>

        {% endif %}

      {% endif %}

    {% endfor %}

  </div>

</div>


<!-- =========================
     Lightbox HTML
     ========================= -->

<div class="lightbox-overlay" id="photoLightbox">

  <button
    class="lightbox-close"
    id="lightboxClose"
    aria-label="Close"
  >
    ×
  </button>

  <button
    class="lightbox-prev"
    id="lightboxPrev"
    aria-label="Previous photo"
  >
    ‹
  </button>

  <div class="lightbox-content">

    <img
      id="lightboxImage"
      src=""
      alt=""
    >

    <div
      class="lightbox-caption"
      id="lightboxCaption"
    ></div>

  </div>

  <button
    class="lightbox-next"
    id="lightboxNext"
    aria-label="Next photo"
  >
    ›
  </button>

</div>


<!-- =========================
     Lightbox JavaScript
     ========================= -->

<script>
document.addEventListener("DOMContentLoaded", function () {

  const thumbnails = Array.from(
    document.querySelectorAll(".photo-thumb")
  );

  const lightbox = document.getElementById("photoLightbox");
  const lightboxImage = document.getElementById("lightboxImage");
  const lightboxCaption = document.getElementById("lightboxCaption");

  const closeButton = document.getElementById("lightboxClose");
  const previousButton = document.getElementById("lightboxPrev");
  const nextButton = document.getElementById("lightboxNext");

  let currentIndex = 0;


  /* Open lightbox */

  function openLightbox(index) {

    if (thumbnails.length === 0) {
      return;
    }

    currentIndex = index;

    const photo = thumbnails[currentIndex];

    const imagePath = photo.dataset.full;
    const caption = photo.dataset.caption;

    lightboxImage.src = imagePath;
    lightboxImage.alt = caption;
    lightboxCaption.textContent = caption;

    lightbox.classList.add("open");

    document.body.style.overflow = "hidden";
  }


  /* Close lightbox */

  function closeLightbox() {

    lightbox.classList.remove("open");

    document.body.style.overflow = "";

    /*
     * Clear image after the fade-out.
     * This prevents the previous image from
     * remaining in memory unnecessarily.
     */

    setTimeout(function () {
      if (!lightbox.classList.contains("open")) {
        lightboxImage.src = "";
      }
    }, 200);
  }


  /* Show previous image */

  function showPrevious() {

    currentIndex =
      (currentIndex - 1 + thumbnails.length)
      % thumbnails.length;

    openLightbox(currentIndex);
  }


  /* Show next image */

  function showNext() {

    currentIndex =
      (currentIndex + 1)
      % thumbnails.length;

    openLightbox(currentIndex);
  }


  /* Click on thumbnail */

  thumbnails.forEach(function (thumbnail, index) {

    thumbnail.addEventListener("click", function () {

      openLightbox(index);

    });

  });


  /* Buttons */

  closeButton.addEventListener(
    "click",
    closeLightbox
  );

  previousButton.addEventListener(
    "click",
    showPrevious
  );

  nextButton.addEventListener(
    "click",
    showNext
  );


  /* Click outside image to close */

  lightbox.addEventListener(
    "click",
    function (event) {

      if (event.target === lightbox) {
        closeLightbox();
      }

    }
  );


  /* Keyboard controls */

  document.addEventListener(
    "keydown",
    function (event) {

      if (!lightbox.classList.contains("open")) {
        return;
      }

      if (event.key === "Escape") {
        closeLightbox();
      }

      if (event.key === "ArrowLeft") {
        showPrevious();
      }

      if (event.key === "ArrowRight") {
        showNext();
      }

    }
  );

});
</script>
