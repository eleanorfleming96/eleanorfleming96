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
  cursor: pointer; /* Show pointer on hover */
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

/* Modal styles */
.modal {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  z-index: 1000;
  cursor: pointer;
}
.modal-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: 90%;
  max-height: 90vh;
}
.modal-content img {
  width: 100%;
  height: auto;
  max-height: 90vh;
  object-fit: contain;
}
.modal-caption {
  position: absolute;
  bottom: 20px;
  left: 0;
  right: 0;
  color: white;
  text-align: center;
  padding: 10px;
  background: rgba(0, 0, 0, 0.7);
}
.close {
  position: absolute;
  top: 15px;
  right: 35px;
  color: #f1f1f1;
  font-size: 40px;
  font-weight: bold;
  cursor: pointer;
}
</style>

<!-- Modal -->
<div id="imageModal" class="modal">
  <span class="close">&times;</span>
  <div class="modal-content">
    <img id="modalImage" src="" alt="">
    <div id="modalCaption" class="modal-caption"></div>
  </div>
</div>

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

<script>
// Get the modal
var modal = document.getElementById("imageModal");
var modalImg = document.getElementById("modalImage");
var modalCaption = document.getElementById("modalCaption");
var closeBtn = document.getElementsByClassName("close")[0];
var currentIndex = 0;
var images = [];

// Collect all images and their captions
document.querySelectorAll('.collage-item').forEach((item, index) => {
  images.push({
    src: item.querySelector('img').src,
    caption: item.querySelector('.caption').innerHTML
  });
  
  item.onclick = function() {
    currentIndex = index;
    showImage(currentIndex);
    modal.style.display = "block";
  }
});

function showImage(index) {
  modalImg.src = images[index].src;
  modalCaption.innerHTML = images[index].caption;
}

function nextImage() {
  currentIndex = (currentIndex + 1) % images.length;
  showImage(currentIndex);
}

function previousImage() {
  currentIndex = (currentIndex - 1 + images.length) % images.length;
  showImage(currentIndex);
}

// Close modal when clicking X
closeBtn.onclick = function() {
  modal.style.display = "none";
}

// Close modal when clicking outside the image
modal.onclick = function(event) {
  if (event.target === modal) {
    modal.style.display = "none";
  }
}

// Handle keyboard navigation
document.addEventListener('keydown', function(event) {
  if (modal.style.display === "block") {
    switch(event.key) {
      case "Escape":
        modal.style.display = "none";
        break;
      case "ArrowLeft":
        previousImage();
        break;
      case "ArrowRight":
        nextImage();
        break;
    }
  }
});
</script>
