<template>
  <header class="header">
    <div class="header__logo">
      <div class="burger"></div>
      <LogoVue :backgroundImage="backgroundSrcImage" linkTo="/" />
    </div>
    <div class="header__menu"><slot></slot></div>
  </header>
</template>
<script>
import LogoVue from "@/components/Logo.vue";
export default {
  name: "HeaderVue",

  components: {
    LogoVue,
  },

  data(){
    return {
      backgroundSrcImage:'logo.png'
    }
  }
};
</script>