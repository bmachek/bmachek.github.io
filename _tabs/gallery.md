---
icon: fas fa-images
title: Gallery
permalink: /gallery/
order: 8
description: Photography by Bastian Machek — landscape, portrait, urban, and macro.
---

{% assign cats = site.data.gallery | map: "category" | uniq | sort %}

<div class="gallery-filters">
  <button class="gallery-filter active" data-cat="all">Alle</button>
  {% for cat in cats %}
  <button class="gallery-filter" data-cat="{{ cat }}">{{ cat }}</button>
  {% endfor %}
</div>

<div class="gallery-grid">
  {% for photo in site.data.gallery %}
  <div class="gallery-item"
       data-url="{{ photo.url }}"
       data-title="{{ photo.title }}"
       data-desc="{{ photo.desc | default: '' }}"
       data-cat="{{ photo.category }}">
    <img src="{{ photo.thumb | default: photo.url }}"
         alt="{{ photo.title }}"
         loading="lazy">
    <div class="gallery-caption">{{ photo.title }}</div>
  </div>
  {% endfor %}
</div>

<div class="gallery-lb" id="gallery-lb" role="dialog" aria-modal="true" aria-label="Lightbox">
  <button class="lb-close" id="lb-close" aria-label="Schließen">✕</button>
  <button class="lb-nav-btn lb-prev" id="lb-prev" aria-label="Vorheriges Bild">&#8249;</button>
  <div class="lb-img-wrap" id="lb-img-wrap"></div>
  <div class="lb-meta">
    <span id="lb-title"></span><span class="lb-desc" id="lb-desc"></span>
  </div>
  <button class="lb-nav-btn lb-next" id="lb-next" aria-label="Nächstes Bild">&#8250;</button>
</div>

<script>
(function () {
  var lb = document.getElementById('gallery-lb');
  var lbWrap = document.getElementById('lb-img-wrap');
  var lbTitle = document.getElementById('lb-title');
  var lbDesc = document.getElementById('lb-desc');

  // Create the img element dynamically so Chirpy's refactor-content.html
  // (which drops <img> tags without src and all subsequent content) never sees it.
  var lbImg = document.createElement('img');
  lbImg.className = 'lb-img';
  lbWrap.appendChild(lbImg);

  function getVisible() {
    return Array.from(document.querySelectorAll('.gallery-item:not(.hidden)'));
  }

  var current = 0;

  function openLb(idx) {
    var visible = getVisible();
    current = Math.max(0, Math.min(idx, visible.length - 1));
    var item = visible[current];
    lbImg.src = item.dataset.url;
    lbImg.alt = item.dataset.title;
    lbTitle.textContent = item.dataset.title;
    lbDesc.textContent = item.dataset.desc ? ' — ' + item.dataset.desc : '';
    lb.classList.add('open');
    document.body.style.overflow = 'hidden';
  }

  function closeLb() {
    lb.classList.remove('open');
    lbImg.src = '';
    document.body.style.overflow = '';
  }

  function navigate(dir) {
    var visible = getVisible();
    current = (current + dir + visible.length) % visible.length;
    var item = visible[current];
    lbImg.src = '';
    lbImg.src = item.dataset.url;
    lbImg.alt = item.dataset.title;
    lbTitle.textContent = item.dataset.title;
    lbDesc.textContent = item.dataset.desc ? ' — ' + item.dataset.desc : '';
  }

  // Use capture phase so our handler runs before GLightbox's bubble-phase handler
  // on the <a class="popup"> anchors Chirpy injects around thumbnail images.
  document.querySelectorAll('.gallery-item').forEach(function (item) {
    item.addEventListener('click', function (e) {
      e.preventDefault();
      e.stopPropagation();
      var visible = getVisible();
      var idx = visible.indexOf(item);
      openLb(idx >= 0 ? idx : 0);
    }, true);
  });

  document.querySelectorAll('.gallery-filter').forEach(function (btn) {
    btn.addEventListener('click', function () {
      var cat = btn.dataset.cat;
      document.querySelectorAll('.gallery-filter').forEach(function (b) {
        b.classList.remove('active');
      });
      btn.classList.add('active');
      document.querySelectorAll('.gallery-item').forEach(function (item) {
        if (cat === 'all' || item.dataset.cat === cat) {
          item.classList.remove('hidden');
        } else {
          item.classList.add('hidden');
        }
      });
    });
  });

  document.getElementById('lb-close').addEventListener('click', closeLb);
  document.getElementById('lb-prev').addEventListener('click', function () { navigate(-1); });
  document.getElementById('lb-next').addEventListener('click', function () { navigate(1); });

  lb.addEventListener('click', function (e) {
    if (e.target === lb) closeLb();
  });

  document.addEventListener('keydown', function (e) {
    if (!lb.classList.contains('open')) return;
    if (e.key === 'Escape') closeLb();
    if (e.key === 'ArrowLeft') navigate(-1);
    if (e.key === 'ArrowRight') navigate(1);
  });
})();
</script>
