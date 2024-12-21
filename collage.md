---
layout: page
title: Adventures
---

<style>
.collage-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  margin: 20px 0 20px 0;  
  padding: 0;  
  max-width: calc(100% - 30px);  
  margin-left: 0px;  
}
.collage-item {
  position: relative;
  overflow: hidden;
  border-radius: 12px;
  aspect-ratio: 1;  
}
.collage-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}
.collage-item:hover img {
  transform: scale(1.1);
}
.caption {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.7);
  color: white;
  padding: 8px;
  text-align: center;
  transform: translateY(100%);
  transition: transform 0.3s ease;
}
.collage-item:hover .caption {
  transform: translateY(0);
}
</style>

<div class="collage-grid">
  <div class="collage-item">
    <img src="/public/images/collage/1.png" alt="Fun 1">
    <div class="caption">Caption 1</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/2.png" alt="Fun 2">
    <div class="caption">Caption 2</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/3.png" alt="Fun 3">
    <div class="caption">Caption 3</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/4.png" alt="Fun 4">
    <div class="caption">Caption 4</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/5.png" alt="Fun 5">
    <div class="caption">Caption 5</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/6.png" alt="Fun 6">
    <div class="caption">Caption 6</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/7.png" alt="Fun 7">
    <div class="caption">Caption 7</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/8.png" alt="Fun 8">
    <div class="caption">Caption 8</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/9.png" alt="Fun 9">
    <div class="caption">Caption 9</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/10.png" alt="Fun 10">
    <div class="caption">Caption 10</div>
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/11.png" alt="Fun 11">
    <div class="caption">Caption 11</div>
  </div>
  <!-- Add more items as needed -->
</div>
