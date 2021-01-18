<template>
  <div class="first-screen">
    <the-header class="first-screen__header container" />

    <div class="first-screen__content container">
      <h1 class="first-screen__title">CreativE DIGITAL Project</h1>
      <span class="first-screen__subtitle"
        >Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget
        lacinia odio sem nec elit.</span
      >
    </div>
  </div>
</template>

<script>
import TheHeader from "../../components/TheHeader";

export default {
  name: "FirstScreen",
  components: {
    TheHeader,
  },
};
</script>

<style lang="scss">
@import "../../styles/sections/firstScreen.scss";
</style>