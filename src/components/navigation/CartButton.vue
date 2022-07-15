<template>
  <BaseButton>
    <IconCart />
  </BaseButton>
</template>

<script>
import BaseButton from '@/components/ui/BaseButton.vue';
import IconCart from '@/components/icons/IconCart.vue';

export default {
  name: "CartButton",

  components: {
    BaseButton,
    IconCart,
  },
};
</script>
