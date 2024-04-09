<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Image Slider</title>
<style>
  .slider-container {

    ![image](https://github.com/akmj3011/kfd/assets/128561949/abd8ed11-27bd-411c-bc45-5c445e12e78c)

    position: relative;
    width: 100%;
    max-width: 100%;
    overflow: hidden;
  }
  .slides {
    display: flex;
    transition: transform 0.5s ease;
  }
  .slide {
    min-width: 100%;
    overflow: hidden;
  }
  .slide img {
    width: 100%;
    height: auto;
  }
  .arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
    padding: 10px;
    background-color: rgba(255, 255, 255, 0.5);
    border: none;
    outline: none;
    z-index: 1;
  }
  .prev {
    left: 0;
  }
  .next {
    right: 0;
  }
</style>
</head>
<body>

<div class="slider-container">
  <div class="slides">
    <div class="slide">
      <img src="image1.jpg" alt="Image 1">
    </div>
    <div class="slide">
      <img src="image2.jpg" alt="Image 2">
    </div>
    <div class="slide">
      <img src="image3.jpg" alt="Image 3">
    </div>
    <!-- Add more slides as needed -->
  </div>
  <button class="arrow prev" onclick="prevSlide()">&#10094;</button>
  <button class="arrow next" onclick="nextSlide()">&#10095;</button>
</div>

<script>
  let slideIndex = 0;
  const slides = document.querySelectorAll('.slide');
  const slideWidth = slides[0].clientWidth;
  const totalSlides = slides.length;
  
  function showSlides() {
    slideIndex++;
    if (slideIndex >= totalSlides) {
      slideIndex = 0;
    }
    const slidePosition = -slideIndex * slideWidth;
    document.querySelector('.slides').style.transform = `translateX(${slidePosition}px)`;
    setTimeout(showSlides, 2000); // Change image every 2 seconds
  }
  
  function nextSlide() {
    slideIndex++;
    if (slideIndex >= totalSlides) {
      slideIndex = 0;
    }
    const slidePosition = -slideIndex * slideWidth;
    document.querySelector('.slides').style.transform = `translateX(${slidePosition}px)`;
  }
  
  function prevSlide() {
    slideIndex--;
    if (slideIndex < 0) {
      slideIndex = totalSlides - 1;
    }
    const slidePosition = -slideIndex * slideWidth;
    document.querySelector('.slides').style.transform = `translateX(${slidePosition}px)`;
  }
  
  showSlides();
</script>

</body>
</html>
