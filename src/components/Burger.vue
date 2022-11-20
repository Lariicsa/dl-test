<template>
  <div class="burger" :class="{ active: isActive }" @click="clickburger"></div>
</template>
<script>
export default {
  name: "BurgerVue",

  props: {
    isActive: {
      type: Boolean,
      default: false,
    },
  },

  methods: {
    clickburger() {
      this.$emit("clickburger");
    },
  },
};
</script>