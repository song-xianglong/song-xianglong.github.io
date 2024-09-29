---
layout: archive
permalink: /gallery/
title: " "
author_profile: true
---

<style>
.event-slider {
  text-align: center;
  margin-bottom: 20px;
}

.slides-container img {
  width: 100%;
  max-width: 600px;  // 根据需要调整
}

button {
  padding: 10px;
  margin: 5px;
  font-size: 16px;
}
</style>

<div class="event-slider">
  <h3>At Nankai</h3>
  <div class="slides-container" id="nankai-slider">
    <img src="../images/IMG_1443.jpeg" alt="Nankai Event Photo 1">
    <img src="../images/IMG_1254.jpeg" alt="Nankai Event Photo 2" style="display: none;">
    <!-- 更多图片 -->
  </div>
  <button onclick="previousImage('nankai-slider')">‹</button>
  <button onclick="nextImage('nankai-slider')">›</button>
</div>

<script>
function nextImage(sliderId) {
  let container = document.getElementById(sliderId);
  let images = container.getElementsByTagName('img');
  let total = images.length;
  let index = findVisibleImage(images);
  if (index >= 0) {
    images[index].style.display = 'none';
    let nextIndex = (index + 1) % total;
    images[nextIndex].style.display = 'block';
  }
}

function previousImage(sliderId) {
  let container = document.getElementById(sliderId);
  let images = container.getElementsByTagName('img');
  let total = images.length;
  let index = findVisibleImage(images);
  if (index >= 0) {
    images[index].style.display = 'none';
    let prevIndex = (index - 1 + total) % total;
    images[prevIndex].style.display = 'block';
  }
}

function findVisibleImage(images) {
  for (let i = 0; i < images.length; i++) {
    if (images[i].style.display !== 'none') {
      return i;
    }
  }
  return -1;  // If no image is visible or all are set to display: none initially
}
</script>