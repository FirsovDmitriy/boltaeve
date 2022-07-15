<template>
  <BaseButton>
    <IconPerson />
  </BaseButton>
</template>

<script>
import BaseButton from "@/components/ui/BaseButton.vue";
import IconPerson from "@/components/icons/IconPerson.vue";

export default {
  name: "AuthButton",

  components: {
    BaseButton,
    IconPerson,
  },
};
</script>
