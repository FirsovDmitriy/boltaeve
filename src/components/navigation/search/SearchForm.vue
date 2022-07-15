<template>
  <div class="search-form__block">
    <div class="search-form__row">
      <BaseControl class="search-form__control" placeholder="Search" />
    </div>
  </div>
</template>

<script>
import BaseControl from "@/components/ui/BaseControl.vue";

export default {
  components: {
    BaseControl,
  },
};
</script>

<style lang="scss" scoped>
.search-form__block {}
</style>
