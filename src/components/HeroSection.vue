<template>
    <section class="herosection">
      <div class="content-container">
        <h1 class="heading">Schedule a video call with the world's experts for advice</h1>
        <p class="description">
          Connect with top industry professionals and gain insights from the best.
        </p>
        <button class="cta-button">Find an Expert</button>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'HeroSection',
  }
  </script>
  
  <style scoped>
  .herosection {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    height: 100vh;
    background: url('../assets/Hero Image-2.png') no-repeat center center;
    background-size: cover;
    position: relative;
  }
  
  .content-container {
    background: rgba(255, 255, 255, 0.5);
    padding: 2rem;
    max-width: 850px;
    text-align: left;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
  }
  
  .heading {
    font-size: 5rem;
    color: #004085;
    margin-bottom: 1rem;
  }
  
  .description {
    font-size: 2rem;
    color: #333;
    margin-bottom: 1.5rem;
  }
  
  .cta-button {
    background-color: #004085;
    color: #fff;
    border: none;
    padding: 0.8rem 1.5rem;
    font-size: 1rem;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .cta-button:hover {
    background-color: #003366;
  }

  @media screen and (max-width: 768px) {
    .herosection {
      justify-content: center;
    }
  
    .content-container {
      margin: 2rem;
    }
  
    .heading {
      font-size: 3rem;
    }
  
    .description {
      font-size: 1.5rem;
    }
  
    .cta-button {
      font-size: 1.2rem;
    }
  }
  
  </style>
  