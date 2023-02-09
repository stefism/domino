<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <header>
    <div class="container clear">
      <div class="logo">
        <img :src="logoIcon" alt="" />
      </div>
      <div class="nav">
        <img :src="menuIcon" alt="" />
      </div>
    </div>
  </header>
</template>

<script>
import Logo from "@/assets/images/logo.png";
import Menu from "@/assets/images/menu.png";

export default {
  data() {
    return {
      logoIcon: Logo,
      menuIcon: Menu,
    };
  },
};
</script>

<style>
</style>