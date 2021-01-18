<template>
  <div class="our-services container" id="services">
    <ul class="our-services__cards">
      <li class="our-services__cards-item">
        <img
          src="../../assets/svg/Icon-Graphic.svg"
          alt="card-img"
          class="our-services__cards-item-img"
        />
        <span class="our-services__cards-item-title">GRAPHIC DESIGN</span>
        <span class="our-services__cards-item-subtitle">{{ subtitle }}</span>
      </li>
      <li class="our-services__cards-item">
        <img
          src="../../assets/svg/Icon-Web.svg"
          alt="card-img"
          class="our-services__cards-item-img"
        />
        <span class="our-services__cards-item-title">WEB DEVELOPMENT</span>
        <span class="our-services__cards-item-subtitle">{{ subtitle }}</span>
      </li>
      <li class="our-services__cards-item">
        <img
          src="../../assets/svg/Icon-SEO.svg"
          alt="card-img"
          class="our-services__cards-item-img"
        />
        <span class="our-services__cards-item-title">SEO MARKETING</span>
        <span class="our-services__cards-item-subtitle">{{ subtitle }}</span>
      </li>
      <li class="our-services__cards-item">
        <img
          src="../../assets/svg/Icon-Mobile.svg"
          alt="card-img"
          class="our-services__cards-item-img"
        />
        <span class="our-services__cards-item-title">MOBILE DEVELOPMENT</span>
        <span class="our-services__cards-item-subtitle">{{ subtitle }}</span>
      </li>
    </ul>
    <div class="our-services__wrapper">
      <img
        src="../../assets/svg/Icon-Services.svg"
        alt="services-icon"
        class="our-services__wrapper-img"
      />
      <h2 class="our-services__wrapper-title">OUR SERVICES</h2>
      <span class="our-services__wrapper-subtitle"
        >“Nullam quis risus eget urna mollis ornare vel eu leo. Nulla vitae elit
        libero, a pharetra augue.” - Borat -</span
      >
    </div>
  </div>
</template>
<script>
export default {
  name: "OurServices",
  data() {
    return {
      subtitle: "Cras mattis consectetur purus sit amet fermentum.",
    };
  },
};
</script>
<style lang="scss">
@import "../../styles/sections/ourServices.scss";
</style>