<template>
  <div>
    <Header />
    <Carousel />
    <div>
      Content
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Carousel from "@/components/Slider.vue";
import Footer from "@/components/Footer.vue";
export default {
  components: { Header, Footer, Carousel }
}
</script>

<style>
   @import "./assets/style.css";
</style>