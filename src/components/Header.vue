<template>
  <header class="header">
    <div class="header__logo">
      <BurgerVue  @clickburger="activeBurgerButton" />
      <LogoVue :backgroundImage="backgroundSrcImage" linkTo="/" />
    </div>
    <div class="header__menu"><slot></slot></div>
  </header>
</template>
<script>
import BurgerVue from "./Burger";
import LogoVue from "@/components/Logo.vue";
export default {
  name: "HeaderVue",

  components: {
    BurgerVue,
    LogoVue,
  },


  data() {
    return {
      backgroundSrcImage: "logo.png",
    };
  },

  methods: {
    activeBurgerButton() {
      this.$emit("activeBurgerButton");
    },
  },
};
</script>