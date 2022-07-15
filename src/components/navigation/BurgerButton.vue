<template>
  <button
    @click="openNavMenu"
    class="burger-button"
    :class="{
      burgerClose: isVisible,
    }"
  >
    <span class="burger-button__line"></span>
    <span class="burger-button__line"></span>
  </button>
</template>

<script>
export default {
  name: "BurgerButton",

  props: {
    isVisible: {
      type: Boolean,
      default: false,
    },
  },

  data() {
    return {};
  },

  methods: {
    openNavMenu() {
      this.$emit("open-nav-menu");
    },
  },
};
</script>

<style lang="scss" scoped>
.burger-button {
  position: relative;
  z-index: 3;

  @media (min-width: 992px) {
    display: none;
  }
}
.burger-button__line {
  position: absolute;
  width: 24px;
  height: 1.9px;
  background: #fff;
  transition: top 0.4s ease-out, transform 0.1s ease-out;
}

.burger-button__line:nth-child(1) {
  top: -5px;
}

.burger-button__line:nth-child(2) {
  top: 5px;
}

.burgerClose .burger-button__line:nth-child(1),
.burgerClose .burger-button__line:nth-child(2) {
  top: 0;
  background: #000;
}

.burgerClose .burger-button__line:nth-child(1) {
  transform: rotate(45deg);
}

.burgerClose .burger-button__line:nth-child(2) {
  transform: rotate(-45deg);
}
</style>
