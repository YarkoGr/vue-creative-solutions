<template>
  <button class="the-button effect">
    {{ buttonName }}
  </button>
</template>


<script>
export default {
  name: "TheButton",
  props: ["buttonName"],
};
</script>

<style lang="scss">
.the-button {
  min-height: 51px;
  padding: 0 52px;
  border: 1px solid $black;
  background: transparent;
  @include text($h20, 300, $black);
  font-style: italic;
  outline: none;
  cursor: pointer;
  position: relative;
  &.effect:before {
    content: "";
    background: rgba(83, 80, 112, 0.5);
    position: absolute;
    width: 100%;
    height: 5px;
    bottom: 0;
    left: 0;
    border-radius: 2px;
    transform: scaleX(0);
    animation: 1s forwards no-hover-v linear;
    animation-fill-mode: forwards;
  }
  &.effect:hover:before,
  :focus:before {
    animation: 0.5s forwards hover-v linear;
    animation-fill-mode: forwards;
  }
  @keyframes hover-v {
    0% {
      transform: scaleX(0);
      height: 5px;
    }
    45% {
      transform: scaleX(1);
      height: 5px;
    }
    55% {
      height: 5px;
    }
    100% {
      transform: scaleX(1);
      height: 50px;
    }
  }
  @-webkit-keyframes hover-v {
    0% {
      transform: scaleX(0);
      -webkit-transform: scale(0);
      height: 5px;
    }
    45% {
      transform: scaleX(1);
      height: 5px;
    }
    55% {
      height: 5px;
    }
    100% {
      transform: scaleX(1);
      height: 100%;
    }
  }

  @keyframes no-hover-v {
    0% {
      transform: scaleX(1);
      height: 51px;
    }
    45% {
      height: 5px;
    }
    55% {
      transform: scaleX(1);
      height: 5px;
      opacity: 1;
    }

    100% {
      transform: scaleX(0);
      height: 5px;
      opacity: 0.02;
    }
  }
  @-webkit-keyframes no-hover-v {
    0% {
      transform: scaleX(1);
      height: 55px;
    }
    45% {
      height: 5px;
    }
    55% {
      transform: scaleX(1);
      height: 5px;
      opacity: 1;
    }

    100% {
      transform: scaleX(0);
      height: 5px;
      opacity: 0.02;
    }
  }
}
</style>