<template>
  <div class="menulist__wrapper" :class="{ vertical: isVertical }">
    <ul class="menulist" :class="{ vertical: isVertical }">
      <li class="menulist__item" v-for="item in item" :key="item.id">
        <router-link
          class="menulist__link"
          :class="{ vertical: isVertical }"
          :to="item.link"
          >{{ item.name }}
        </router-link>
        <span
          v-if="hasTotal"
          class="menulist__total"
          :class="{ vertical: isVertical }"
          >{{ item.total }}</span
        >
      </li>
      <slot></slot>
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
    hasTotal: {
      type: Boolean,
      default: false,
    },
  },
};
</script>