<template>
  <div class="the-header" :class="{ toScroll: handleScroll > 0 }">
    <a href="/"
      ><img class="the-header__img" src="../assets/svg/Logo.svg" alt="logo"
    /></a>
    <ul class="the-header__list">
      <li
        class="the-header__list-item"
        v-for="(item, idx) in menuItems"
        :key="idx"
      >
        <a class="the-header__list-item-link" :href="item.href">{{
          item.name
        }}</a>
      </li>
    </ul>
    <burger-menu />
  </div>
</template>

<script>
import BurgerMenu from "./BurgerMenu.vue";
import { menuData } from "../data";
export default {
  components: { BurgerMenu },
  name: "TheHeader",
  data() {
    return {
      handleScroll: 0,
      menuItems: menuData,
    };
  },
  created() {
    window.addEventListener("scroll", this.handleScrollBar);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScrollBar);
  },
  methods: {
    handleScrollBar() {
      this.handleScroll = window.scrollY;
    },
  },
};
</script>

<style lang="scss">
.the-header {
  @include flex(space-between);
  padding-top: 25px;
  &__list {
    @include flex(center, center);
    @media screen and (max-width: 730px) {
      display: none;
    }
  }
  &__list-item {
    position: relative;
    overflow: hidden;
    &:after {
      background: $main-color;
      content: "";
      height: 155px;
      left: -75px;
      opacity: 0.8;
      position: absolute;
      top: -50px;
      transform: rotate(35deg);
      transition: all 1550ms cubic-bezier(0.19, 1, 0.22, 1);
      width: 50px;
      z-index: -10;
    }
    &:hover {
      &:after {
        left: 120%;
        transition: all 1550ms cubic-bezier(0.19, 1, 0.22, 1);
      }
    }
  }
  &__list-item:not(:last-child) {
    margin-right: 30px;
  }
  &__list-item-link {
    text-decoration: none;
    @include text($h24, 700);
    text-transform: uppercase;
  }
  .burger-menu {
    display: none;
    @media screen and (max-width: 730px) {
      display: inline;
    }
  }
  .bm-menu {
    z-index: 20;
  }
}
.toScroll {
  background: $card-subtitle;
  z-index: 20;
}
</style>