<template>
  <header class="header">
    <AppContainer>
      <div class="header__row">
        <BurgerButton
          :isVisible="isVisible"
          @open-nav-menu="openNavMenu"
        />
        <div class="header__logo">
          <IconBoltaeva />
        </div>
        <NavMenu :isVisible="isVisible" />
        <div class="header__actions">
          <span class="header__actions-item">
            <SearchFormButton class="header__search" />
          </span>
          <span class="header__actions-item">
            <CartButton class="header__cart-button" />
          </span>
          <span class="header__actions-item">
            <AuthButton class="header__auth" />
          </span>
        </div>
      </div>
    </AppContainer>
  </header>
</template>

<script>
import AppContainer from "@/components/AppContainer.vue";
import BurgerButton from "@/components/navigation/BurgerButton.vue";
import NavMenu from "./NavMenu.vue";
import IconBoltaeva from "../icons/IconBoltaeva.vue";
import CartButton from "./CartButton.vue";
import AuthButton from "./AuthButton.vue";
import SearchFormButton from "@/components/navigation/search/SearchFormButton.vue";

export default {
  name: "TheHeader",

  components: { AppContainer, BurgerButton, NavMenu, IconBoltaeva, CartButton, AuthButton, SearchFormButton },

  data() {
    return {
      isVisible: false,
    };
  },

  methods: {
    openNavMenu() {
      this.isVisible = !this.isVisible;
    },
  },
};
</script>

<style lang="scss" scoped>
.header {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
  width: 100%;
  padding: 30px 0;
}

.header__row {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header__logo {
  position: absolute;
  left: 50%;
  display: flex;
  width: 180px;
  transform: translateX(-50%);
}

.header__logo,
.header__search,
.header__cart-button,
.header__auth {
  color: #fff;
}

.header__actions {
  display: flex;
}

.header__actions-item {
  & + & {
    margin-left: 25px;
  }

  &:nth-child(3) {
    display: none;
  }

  @media (min-width: 992px) {
    &:nth-child(3) {
      display: block;
    }
  }
}

.header__auth {
  @media (min-width: 992px) {
    color: #fff;
  }
}
</style>
