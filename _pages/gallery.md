---
layout: archive
permalink: /gallery/
title: " "
author_profile: true
---

<style>
.event-slider {
  position: relative;
  width: 100%;
  max-width: 600px;
  margin: auto;
  overflow: hidden;
}

.slides-container {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.slides-container img {
  width: 100%;
  flex-shrink: 0;
  max-width: 600px;
}

button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
}

button.prev {
  left: 0;
}

button.next {
  right: 0;
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
let currentIndex = 0;

function moveSlides(direction) {
  const slider = document.getElementById('nankai-slider');
  const slides = slider.getElementsByTagName('img');
  const totalSlides = slides.length;

  // 计算新的索引
  currentIndex = (currentIndex + direction + totalSlides) % totalSlides;

  // 移动幻灯片容器
  slider.style.transform = `translateX(-${currentIndex * 100}%)`;
}
</script>