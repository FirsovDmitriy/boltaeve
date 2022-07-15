<template>
  <footer class="footer">
    <AppContainer class="footer__container">
      <div class="footer__title">
        <IconBoltaeva />
      </div>
    </AppContainer>
  </footer>
</template>

<script>
import AppContainer from "@/components/AppContainer.vue";
import IconBoltaeva from "@/components/icons/IconBoltaeva.vue";

export default {
  name: "TheFooter",

  components: {
    AppContainer,
    IconBoltaeva,
  },
};
</script>

.<style lang="scss" scoped>
.footer {
  &__title {
    display: flex;
    justify-content: center;
    color: #AC8F78;
  }
}
</style>
