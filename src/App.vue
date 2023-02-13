<template>
  <div>
    <Header />
    <div>
      <Carousel />
      <Menu />
      <CallUsIndex />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Carousel from "@/components/Slider.vue";
import Footer from "@/components/Footer.vue";
import Menu from "@/components/Menu.vue";
import CallUsIndex from "@/components/CallUsIndex.vue";

export default {
  components: { Header, Footer, Carousel, Menu, CallUsIndex },
};
</script>

<style>
@import "./assets/style.css";
</style>
