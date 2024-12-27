<template>
    <section class="carousal">
      <div class="carousel-container">
        <div
          class="carousel-track"
          :style="{ transform: `translateX(-${currentIndex * (100 + gapPercentage)}%)` }"
        >
          <div class="carousel-item" v-for="(slide, index) in slides" :key="index">
            <h3>{{ slide.title }}</h3>
            <p>{{ slide.content }}</p>
            <p><strong>{{ slide.author }}</strong></p>
          </div>
        </div>
  
        <div class="carousel-buttons">
          <button class="carousel-button prev" @click="prevSlide">
            &#9664;
          </button>
          <button class="carousel-button next" @click="nextSlide">
            &#9654;
          </button>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "Carousel",
    data() {
      return {
        currentIndex: 0,
        gapPercentage: 5, // Gap percentage for spacing
        slides: [
          {
            title: "Lucas is amazing!",
            content:
              "We covered so much and he opened my eyes to a lot of things I never thought about when it comes to fitness.",
            author: "- John Doe",
          },
          {
            title: "Lucas was great!",
            content:
              "He was a very good listener and helped me have a better view in my goals and how to improve my body. 15 minutes well worth it!",
            author: "- John Doe",
          },
          {
            title: "Incredible Session!",
            content:
              "Lucas provided insights that transformed the way I approach my health and fitness journey.",
            author: "- John Doe",
          },
          {
            title: "Incredible Session!",
            content:
              "Lucas provided insights that transformed the way I approach my health and fitness journey.",
            author: "- John Doe",
          },
          {
            title: "Incredible Session!",
            content:
              "Lucas provided insights that transformed the way I approach my health and fitness journey.",
            author: "- John Doe",
          },
          {
            title: "Incredible Session!",
            content:
              "Lucas provided insights that transformed the way I approach my health and fitness journey.",
            author: "- John Doe",
          },
          {
            title: "Incredible Session!",
            content:
              "Lucas provided insights that transformed the way I approach my health and fitness journey.",
            author: "- John Doe",
          },
        ],
      };
    },
    methods: {
      nextSlide() {
        const totalSlides = this.slides.length;
        const slidesPerView = 2; // Show two slides at a time
        const maxIndex = Math.ceil(totalSlides / slidesPerView) - 1;
        this.currentIndex = (this.currentIndex + 1) % (maxIndex + 1);
      },
      prevSlide() {
        const totalSlides = this.slides.length;
        const slidesPerView = 2;
        const maxIndex = Math.ceil(totalSlides / slidesPerView) - 1;
        this.currentIndex =
          (this.currentIndex - 1 + (maxIndex + 1)) % (maxIndex + 1);
      },
    },
  };
  </script>
  
  <style scoped>
  .carousal {
    background-color: rgb(150, 197, 199);
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .carousel-container {
    position: relative;
    width: 90%; /* Extended width to 90% */
    max-width: 1200px;
    height: 550px;
    overflow: hidden;
    margin: 0 auto;
    
    border-radius: 8px;
    
    padding: 50px;
  }
  
  .carousel-track {
    display: flex;
    transition: transform 0.5s ease-in-out;
    gap: 5%; /* Adjust gap between items */
  }
  
  .carousel-item {
    min-width: calc((100% - 5%) / 2); /* Adjust width for two items with gap */
    box-sizing: border-box;
    text-align: center;
    padding: 20px;
    background-color: white;
    height: 400px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .carousel-item h3 {
    margin-bottom: 10px;
    font-size: 18px;
  }
  
  .carousel-item p {
    color: #555;
    font-size: 14px;
    line-height: 1.5;
  }
  
  .carousel-buttons {
    display: flex;
    justify-content: center;
    margin-top: 20px;
  }
  
  .carousel-button {
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    font-size: 18px;
    cursor: pointer;
    margin: 0 10px;
  }
  
  .carousel-button:hover {
    background-color: #0056b3;
  }
  </style>
  