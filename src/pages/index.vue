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
  import Navbar from '@/components/Navbar.vue'
  import HeroSection from '@/components/HeroSection.vue'
  import AboutUs from '@/components/about.vue'
  import Done from '@/components/Done.vue'
  import Carousal from '@/components/carousal.vue'
  import Footer from '@/components/Footer.vue'

</script>

<style scoped>
hr{
  width: 100%;
  margin-top: 50px;
  
  opacity: 0.5;
}
</style>
