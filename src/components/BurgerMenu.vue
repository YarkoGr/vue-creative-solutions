<template>
  <div class="burger-menu">
    <Slide right>
      <a
        class="the-header__list-item-link"
        :menuItems="menuItems"
        v-for="(item, idx) in menuItems"
        :key="idx"
        :href="item.href"
        >{{ item.name }}</a
      >
    </Slide>
  </div>
</template>
<script>
import { Slide } from "vue-burger-menu";
import { menuData } from "../data";
export default {
  name: "BurgerMenu",
  components: {
    Slide,
  },
  data() {
    return {
      menuItems: menuData,
    };
  },
};
</script>
<style lang="scss">
.bm-menu,
.bm-burger-bars {
  background-color: $main-color;
}
.bm-burger-bars {
  border: 1px solid $black;
}
</style>