<template>
  <BaseButton class="search-form-btn">
    <IconSearch />
  </BaseButton>
</template>

<script>
import BaseButton from '@/components/ui/BaseButton.vue';
import IconSearch from '@/components/icons/IconSearch.vue';

export default {
  components: {
    BaseButton,
    IconSearch,
},
};
</script>

<style lang="scss" scoped>
.search-form-btn {
  display: none;
  @media (min-width: 992px) {
    display: flex;
  }
}
</style>
