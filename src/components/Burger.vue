<template>
  <div class="burger" :class="{ active: isActive }" @click="clickburger"></div>
</template>
<script>
export default {
  name: "BurgerVue",

  data() {
    return {
      isActive: false,
    };
  },

  methods: {
    clickburger() {
      this.isActive = !this.isActive;
    },
  },
};
</script>