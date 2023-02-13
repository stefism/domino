<template>
  <div class="anim_container">
    <transition @before-enter="beforeEnter" @enter="enter" appear>
      <div class="icon icon_phone" delay="0" left="100"></div>
    </transition>

    <transition @before-enter="beforeEnter" @enter="enter" appear>
      <div class="plus one" delay="100" left="310">+</div>
    </transition>

    <transition @before-enter="beforeEnter" @enter="enter" appear>
      <div class="icon icon_delivery" delay="200" left="480"></div>
    </transition>

    <transition @before-enter="beforeEnter" @enter="enter" appear>
      <div class="plus" delay="300" left="750">=</div>
    </transition>

    <transition @before-enter="beforeEnter" @enter="enter" appear>
      <div class="icon icon_pizza" delay="400" left="900"></div>
    </transition>
  </div>
</template>

<script>
export default {
  methods: {
    beforeEnter(element) {
      element.style.left = "-200px";
      element.style.opacity = 0;
    },
    enter(element, done) {
      let delay = parseInt(element.getAttribute("delay"));
      let left = parseInt(element.getAttribute("left"));

      // eslint-disable-next-line no-undef
      Velocity(
        element,
        { opacity: 1, left },
        { delay, duration: 2000, complete: done }
      );
    },
  },
};
</script>

<style>
.anim_container {
  position: relative;
  height: 200px;
}

.icon {
  background-size: cover !important;
  position: absolute;
}

.plus {
  position: absolute;
  font-size: 160px;
  color: white;
  top: 90px;
}

.icon_phone {
  background: url("@/assets/images/icons/icon-phone.png");
  width: 130px;
  height: 130px;
  top: 30px;
}

.icon_delivery {
  background: url("@/assets/images/icons/icon-delivery.png");
  width: 200px;
  height: 200px;
}

.icon_pizza {
  background: url("@/assets/images/icons/icon-pizza.png");
  width: 200px;
  height: 200px;
}
</style>
