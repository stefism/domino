<template>
  <div>
    <Header />
    <div>
      <Carousel />
      <Menu />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Carousel from "@/components/Slider.vue";
import Footer from "@/components/Footer.vue";
import Menu from "@/components/Menu.vue";

export default {
  components: { Header, Footer, Carousel, Menu }
}
</script>

<style>
   @import "./assets/style.css";
</style>