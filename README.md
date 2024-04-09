

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

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

      ![image](https://github.com/akmj3011/kfd/assets/128561949/8371f8ae-fc67-4fa9-8e49-e49d50577e30 >  
![image](https://github.com/akmj3011/kfd/assets/128561949/a16baf8e-f276-4f4a-836a-78ab108601ae)
![image](https://github.com/akmj3011/kfd/assets/128561949/c0d6ff0a-60fa-42f1-885d-6c0af093b65f)>

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
 




