// script.js


// Slider Functionality
let currentSlide = 0;
const slides = document.querySelectorAll(".slide");


function showSlide(index) {
  slides.forEach((slide, i) => {
    slide.style.transform = `translateX(-${index * 100}%)`;
  });
}


setInterval(() => {
  currentSlide = (currentSlide + 1) % slides.length;
  showSlide(currentSlide);
}, 3000);


// Form Submission
const contactForm = document.getElementById("contactForm");
const formResponse = document.getElementById("formResponse");


contactForm.addEventListener("submit", (event) => {
  event.preventDefault();
  formResponse.textContent = "Thank you for contacting us, " + contactForm.name.value + "!";
  contactForm.reset();
});