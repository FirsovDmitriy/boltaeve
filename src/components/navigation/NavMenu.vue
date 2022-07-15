<template>
  <div
    class="nav-menu"
    :class="{
      navMenuVisible: isVisible,
    }"
  >
    <div class="nav-menu__body">
      <div class="nav-menu__header">
        <SearchFormButton class="nav-menu__search-button" />
        <div class="nav-menu__logo">
          <IconBoltaeva />
        </div>
        <AuthButton />
        <CartButton class="nav-menu__cart-btn" />
      </div>
      <nav class="nav-menu__block">
        <ul class="nav-menu__list">
          <li
            v-for="item in list"
            :key="item.text"
            class="nav-menu__item"
            :class="{
              hiddenItem: item.hidden,
            }"
          >
            <router-link class="nav-menu__link" to="/"> {{ item.text }} </router-link>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>

<script>
import { list } from "./list";
import IconBoltaeva from "../icons/IconBoltaeva.vue";
import CartButton from "./CartButton.vue";
import AuthButton from "./AuthButton.vue";
import SearchFormButton from "@/components/navigation/search/SearchFormButton.vue";

export default {
  name: "NavMenu",

  props: {
    isVisible: {
      type: Boolean,
      default: false,
    },
  },

  data() {
    return {
      list,
    };
  },

  components: { IconBoltaeva, CartButton, AuthButton, SearchFormButton },
};
</script>

<style lang="scss" scoped>
.nav-menu {
  @media (min-width: 0px) and (max-width: 992px) {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -2;
    width: 100%;
    height: 100%;
    background: #F5ECE3;
    opacity: 0;
    transform: translateY(-10%);
    transition: opacity 0.2s ease-out, transform 0.1s ease-in-out;
  }

  width: 100%;
}

.navMenuVisible {
  z-index: 2;
  opacity: 1;
  transform: translateY(0);
}
.nav-menu__header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 30px 0;

  @media (min-width: 992px) {
    display: none;
  }
}

.nav-menu__search-button {
  display: flex;
  margin: 0 auto 0 80px;
  @media (min-width: 992px) {
    display: none;
  }
}

.nav-menu__logo {
  position: absolute;
  left: calc(50% - 55px);
  display: flex;
  width: 110px;
  height: 10px;
  color: #555;
}

.nav-menu__cart-btn {
  margin: 0 30px;
}

.nav-menu__block {
  margin-top: 40px;

  @media (min-width: 992px) {
    margin: 0;
  }
}

.nav-menu__list {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 40px 0 0 0;

  @media (min-width: 992px) {
    flex-direction: row;
    margin: 0;
  }
}

.nav-menu__item {
  &:not(:last-child) {
    margin: 0 0 34px 0;
  }

  @media (min-width: 992px) {
    &:not(:last-child) {
      margin: 0 47px 0 0;
    }

    &:nth-child(4) {
      margin-right: auto;
    }
  }
}

.nav-menu__link {
  font-size: 24px;
  line-height: 1.1;
  letter-spacing: -0.03em;

  @media (min-width: 992px) {
    font-size: 14px;
    ine-height: 1.2%;
    color: #fff;
  }
}

@media (min-width: 992px) {
  .hiddenItem {
    display: none;
  }
}
</style>
