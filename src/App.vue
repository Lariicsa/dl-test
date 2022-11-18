<template>
  <div class="space" id="app">
    <router-view />
    <FooterVue></FooterVue>
  </div>
</template>
<script>
import FooterVue from "@/components/Footer";
export default {
  name: "App",

  components: {
    FooterVue,
  },
};
</script>

