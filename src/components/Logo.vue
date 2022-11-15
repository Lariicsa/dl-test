<template>
  <router-link
    class="logo"
    :style="`background-image:url('${backgroundImage}')`"
    :to="linkTo"
  ></router-link>
</template>
<script>
export default {
  name: "LogoVue",

  props: {
    backgroundImage: {
      type: String,
    },
    linkTo: {
      type: String,
      default: '#'
    },
  },
};
</script>