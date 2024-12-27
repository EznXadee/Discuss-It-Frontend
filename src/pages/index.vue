<template>
  <Navbar/>
  <HeroSection/>
  <AboutUs/>
  <hr/>
  <Done/>
  <Carousal/>
  <Footer />
</template>

<script setup>
  import Navbar from '@/components/landingPage/Navbar.vue'
  import HeroSection from '@/components/landingPage/HeroSection.vue'
  import AboutUs from '@/components/landingPage/about.vue'
  import Done from '@/components/landingPage/Done.vue'
  import Carousal from '@/components/landingPage/carousal.vue'
  import Footer from '@/components/landingPage/Footer.vue'

</script>

<style scoped>
hr{
  width: 100%;
  margin-top: 50px;
  
  opacity: 0.5;
}
</style>
