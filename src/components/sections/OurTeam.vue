<template>
  <div class="our-team">
    <img
      src="../../assets/svg/Icon-Team.svg"
      alt="our-team-icon"
      class="our-team__icon"
    />
    <h2 class="our-team__title">MEET OUR TEAM</h2>
    <div class="our-team__carousel">
      <VueSlickCarousel v-bind="value">
        <div
          class="our-team__carousel-card"
          v-for="(item, idx) in cards"
          :key="idx"
        >
          <img
            class="our-team__carousel-card-img"
            :src="item.img"
            :alt="`${item.title}-photo`"
          />

          <div class="our-team__carousel-card-subscribe">
            <h3 class="our-team__carousel-card-title">{{ item.title }}</h3>
            <span class="our-team__carousel-card-subtitle">{{
              item.subtitle
            }}</span>
          </div>
          <social-icons />
        </div>
      </VueSlickCarousel>
    </div>
  </div>
</template>
<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import SocialIcons from "../SocialIcons.vue";
export default {
  name: "OurTeam",
  components: {
    VueSlickCarousel,
    SocialIcons,
  },
  data() {
    return {
      value: {
        arrows: true,
        infinite: true,
        speed: 500,
        focusOnSelect: true,
        slidesToShow: 3,
        slidesToScroll: 1,
        touchThreshold: 5,
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 1,
              infinite: true,
              dots: true,
              arrows: false,
            },
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2,
              initialSlide: 2,
              dots: true,
              arrows: false,
            },
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              dots: true,
              arrows: false,
            },
          },
        ],
      },
      cards: [
        {
          img: require("@/assets/workers/worker1.png"),
          title: "Miguel Obrien",
          subtitle: "CEO & Founder",
        },
        {
          img: require("@/assets/workers/worker2.png"),
          title: "Jackie Carroll",
          subtitle: "Art Director",
        },
        {
          img: require("@/assets/workers/worker3.png"),
          title: "Ida Morrison",
          subtitle: "Designer",
        },
        {
          img: "https://picsum.photos/222/222?random=2",
          title: "Yarik Pasko",
          subtitle: "Front End Developer",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
@import "../../styles/sections/ourTeam.scss";
</style>