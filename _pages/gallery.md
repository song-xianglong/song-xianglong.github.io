---
layout: archive
permalink: /gallery/
title: " "
author_profile: true
---

<style>
* {
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
}

.slideshow-container {
  position: relative;
  max-width: 600px;
  margin: auto;
}

.mySlides {
  display: none;
}

img {
  vertical-align: middle;
  width: 100%;
}

/* 控制按钮的样式 */
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  padding: 16px;
  margin-top: -22px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.8);
}

/* 滑动动画 */
.fade {
  animation-name: fade;
  animation-duration: 1.5s;
}

@keyframes fade {
  from {opacity: .4}
  to {opacity: 1}
}

/* 圆点指示器的样式 */
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active, .dot:hover {
  background-color: #717171;
}
</style>

<div class="slideshow-container">

  <!-- 图片1 -->
  <div class="mySlides fade">
    <img src="../images/IMG_1443.jpeg" alt="Nankai Event Photo 1">
  </div>

  <!-- 图片2 -->
  <div class="mySlides fade">
    <img src="../images/IMG_1254.jpeg" alt="Nankai Event Photo 2">
  </div>

  <!-- 左右控制按钮 -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>

</div>

<!-- 圆点指示器 -->
<div style="text-align:center">
  <span class="dot" onclick="currentSlide(1)"></span> 
  <span class="dot" onclick="currentSlide(2)"></span> 
</div>

<script>
let slideIndex = 1;
showSlides(slideIndex);

// 下一张/上一张控制函数
function plusSlides(n) {
  showSlides(slideIndex += n);
}

// 当前图片控制函数
function currentSlide(n) {
  showSlides(slideIndex = n);
}

// 显示图片函数
function showSlides(n) {
  let i;
  let slides = document.getElementsByClassName("mySlides");
  let dots = document.getElementsByClassName("dot");
  if (n > slides.length) {slideIndex = 1}    
  if (n < 1) {slideIndex = slides.length}
  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";  
  }
  for (i = 0; i < dots.length; i++) {
    dots[i].className = dots[i].className.replace(" active", "");
  }
  slides[slideIndex-1].style.display = "block";  
  dots[slideIndex-1].className += " active";
}
</script>