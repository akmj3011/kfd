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
      <img src="kangaroo1.jpg" alt="Kangaroo 1"> ![image](https://github.com/akmj3011/kfd/assets/128561949/d88a63a6-c36d-496d-b03a-5edbbc88ca56)

    </div>
    <div class="slide">
      <img src="rabbit2.jpg" alt="rabbit"> ![image](https://github.com/akmj3011/kfd/assets/128561949/57000799-e2f2-4511-b64a-7e8cd9e6f238)

    </div>
    <div class="slide">
      <img src="giraffe.jpg" alt="giraffe3"> ![image](https://github.com/akmj3011/kfd/assets/128561949/0eed8ce2-8a76-4457-8749-34459723ed4c)

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
