<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
.btn {
  display: flex;
  transition: all 0.3s ease-in;

  @media (any-hover: hover) {
    &:hover {
      color: #e7d2bd;
    }
  }
}
</style>
