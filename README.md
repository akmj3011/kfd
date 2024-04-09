<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kangaroo Slider</title>
<style>
  .slider-container {
    position: relative;
    width: 100%;
    max-width: 100%;
    overflow: hidden;
    margin: 0 auto;
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
    font-size: 20px;
    color: #333;
  }
  .prev {
    left: 10px;
  }
  .next {
    right: 10px;
  }
</style>
</head>
<body>

<div class="slider-container">
  <div class="slides">
    <!-- Add your images here -->
    <div class="slide">
      <img src="kangaroo1.jpg" alt="Kangaroo 1">
    </div>
    <div class="slide">
      <img src="kangaroo2.jpg" alt="Kangaroo 2">
    </div>
    <div class="slide">
      <img src="kangaroo3.jpg" alt="Kangaroo 3">
    </div>
    <!-- Add more slides as needed -->
  </div>
  <button class="arrow prev" onclick="prevSlide()">&#10094;</button>
  <button class="arrow next" onclick="nextSlide()">&#10095;</button>
</div>

<script>
  let slideIndex = 0;
  const slides = document.querySelectorAll('.slide');
  const totalSlides = slides.length;

  function showSlides() {
    slideIndex++;
    if (slideIndex >= totalSlides) {
      slideIndex = 0;
    }
    const slidePosition = -slideIndex * 100;
    document.querySelector('.slides').style.transform = `translateX(${slidePosition}%)`;
  }

  function nextSlide() {
    slideIndex++;
    if (slideIndex >= totalSlides) {
      slideIndex = 0;
    }
    const slidePosition = -slideIndex * 100;
    document.querySelector('.slides').style.transform = `translateX(${slidePosition}%)`;
  }

  function prevSlide() {
    slideIndex--;
    if (slideIndex < 0) {
      slideIndex = totalSlides - 1;
    }
    const slidePosition = -slideIndex * 100;
    document.querySelector('.slides').style.transform = `translateX(${slidePosition}%)`;
  }

  setInterval(showSlides, 2000);
</script>

</body>
</html>
