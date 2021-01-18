<template>
  <ul class="social-icons">
    <li class="social-icons__item" v-for="(element, idx) in socials" :key="idx">
      <a :href="element.link" target="_blank" class="social-icons__item-link"
        ><img
          :src="element.icon"
          :alt="element.name"
          class="social-icons__item-link-img"
      /></a>
    </li>
  </ul>
</template>
<script>
export default {
  name: "SocialIcons",
  data() {
    return {
      socials: [
        {
          name: "behance",
          icon: require("@/assets/social/behance.png"),
          link: "https://www.behance.net/",
        },
        {
          name: "facebook",
          icon: require("@/assets/social/facebook.png"),
          link: "https://www.facebook.com/",
        },
        {
          name: "google",
          icon: require("@/assets/social/google.png"),
          link: "https://www.google.com.ua",
        },
        {
          name: "linkedin",
          icon: require("@/assets/social/linked-in.png"),
          link: "https://www.linkedin.com",
        },
        {
          name: "twitter",
          icon: require("@/assets/social/twitter.png"),
          link: "https://twitter.com",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.social-icons {
  @include flex(center, center, row, wrap);

  &__item {
    min-width: calc(100% / 5 - 5px);
    @media screen and (max-width: 768px) {
      min-width: calc(100% / 3 - 5px);
    }
    @media screen and (max-width: 425px) {
      min-width: calc(100% / 5 - 5px);
    }
    &:hover {
      -webkit-animation-name: pulse;
      animation-name: pulse;
      -webkit-animation-duration: 1s;
      animation-duration: 1s;
      -webkit-animation-fill-mode: both;
      animation-fill-mode: both;
    }
  }
  @-webkit-keyframes pulse {
    0% {
      -webkit-transform: scale3d(1, 1, 1);
      transform: scale3d(1, 1, 1);
    }
    50% {
      -webkit-transform: scale3d(1.05, 1.05, 1.05);
      transform: scale3d(1.05, 1.05, 1.05);
    }
    100% {
      -webkit-transform: scale3d(1, 1, 1);
      transform: scale3d(1, 1, 1);
    }
  }
  @keyframes pulse {
    0% {
      -webkit-transform: scale3d(1, 1, 1);
      transform: scale3d(1, 1, 1);
    }
    50% {
      -webkit-transform: scale3d(1.05, 1.05, 1.05);
      transform: scale3d(1.05, 1.05, 1.05);
    }
    100% {
      -webkit-transform: scale3d(1, 1, 1);
      transform: scale3d(1, 1, 1);
    }
  }
}
</style>