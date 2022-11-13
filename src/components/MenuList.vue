<template>
  <div class="menulist__wrapper">
    <ul class="menulist" :class="isVertical">
      <li class="menulist__item" v-for="item in item" :key="item.id">
        <router-link class="menulist__link" :to="item.link">{{ item.name }}</router-link>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "LogoVue",

  props: {
    item: {
      type: Array,
    },
    isVertical: {
      type: Boolean,
      default: false,
    },
  },
};
</script>