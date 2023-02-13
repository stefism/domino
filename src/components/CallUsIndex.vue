<template>
  <div class="call_us_container">
    <div class="container">
      <div class="first">
        <h1>Hungry ?</h1>
      </div>
      <div class="second">
        <CallUsAnim />
      </div>
      <div class="third">
        <span>Give us a call:</span> <span>4567-8910</span>
      </div>
    </div>
  </div>
</template>

<script>
import CallUsAnim from "@/components/CallUsAnim.vue";

export default {
  components: { CallUsAnim },
};
</script>

<style></style>
