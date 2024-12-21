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
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.collage-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.collage-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
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
.close {
  position: absolute;
  top: 15px;
  right: 35px;
  color: #f1f1f1;
  font-size: 40px;
  font-weight: bold;
  cursor: pointer;
}
.nav-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    color: white;
    font-size: 30px;
    cursor: pointer;
    padding: 16px;
    background-color: rgba(0, 0, 0, 0.5);
    border: none;
    border-radius: 4px;
}

.prev {
    left: 20px;
}

.next {
    right: 20px;
}
</style>

<!-- Modal -->
<div id="imageModal" class="modal">
  <span class="close">&times;</span>
  <button class="nav-button prev" onclick="changeImage(-1)">&#10094;</button>
  <div class="modal-content">
    <img id="modalImage" src="" alt="">
  </div>
  <button class="nav-button next" onclick="changeImage(1)">&#10095;</button>
</div>

<div class="collage-grid">
  <div class="collage-item">
    <img src="/public/images/collage/1.png" alt="Fun 1">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/23.png" alt="Fun 23">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/2.png" alt="Fun 2">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/8.png" alt="Fun 8">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/10.png" alt="Fun 10">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/16.png" alt="Fun 16">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/4.png" alt="Fun 4">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/5.png" alt="Fun 5">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/6.png" alt="Fun 6">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/7.png" alt="Fun 7">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/9.png" alt="Fun 9">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/3.png" alt="Fun 3">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/11.png" alt="Fun 11">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/12.png" alt="Fun 12">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/14.png" alt="Fun 14">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/15.png" alt="Fun 15">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/17.png" alt="Fun 17">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/18.png" alt="Fun 18">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/19.png" alt="Fun 19">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/20.png" alt="Fun 20">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/21.png" alt="Fun 21">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/22.png" alt="Fun 22">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/24.png" alt="Fun 24">
  </div>
  <div class="collage-item">
    <img src="/public/images/collage/25.png" alt="Fun 25">
  </div>
</div>

<script>
// Get the modal
var modal = document.getElementById("imageModal");
var modalImg = document.getElementById("modalImage");

// Get all images with class collage-item
var images = document.getElementsByClassName("collage-item");

// Add click event to all images
for (var i = 0; i < images.length; i++) {
  images[i].onclick = function() {
    modal.style.display = "block";
    modalImg.src = this.getElementsByTagName('img')[0].src;
    currentImageIndex = Array.from(images).indexOf(this);
    
    // Add keyboard event listener when modal is opened
    document.addEventListener('keydown', handleKeyPress);
  }
}

// Get the <span> element that closes the modal
var span = document.getElementsByClassName("close")[0];

// When the user clicks on <span> (x), close the modal
span.onclick = function() {
  modal.style.display = "none";
  
  // Remove keyboard event listener when modal is closed
  document.removeEventListener('keydown', handleKeyPress);
}

// Close modal when clicking outside the image
modal.onclick = function(event) {
  if (event.target == modal) {
    modal.style.display = "none";
  }
}

// Close modal with escape key
document.addEventListener('keydown', function(event) {
  if (modal.style.display === "block") {
    switch(event.key) {
      case "Escape":
        modal.style.display = "none";
        break;
    }
  }
});

let currentImageIndex = 0;

function changeImage(direction) {
  currentImageIndex += direction;
  
  // Loop around if we reach the end or beginning
  if (currentImageIndex >= images.length) {
    currentImageIndex = 0;
  } else if (currentImageIndex < 0) {
    currentImageIndex = images.length - 1;
  }
  
  modalImg.src = images[currentImageIndex].getElementsByTagName('img')[0].src;
}

function handleKeyPress(event) {
  if (event.key === "ArrowLeft" || event.key === "h") {
    changeImage(-1);
  } else if (event.key === "ArrowRight" || event.key === "l") {
    changeImage(1);
  } else if (event.key === "Escape") {
    modal.style.display = "none";
  }
}
</script>
