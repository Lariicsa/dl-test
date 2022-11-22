<template>
  <div class="menulist__wrapper" :class="typeOfMenu">
    <div v-if="hasFinder" class="menulist__finder">
      <slot name="finder"></slot>
    </div>
    <ul class="menulist" :class="typeOfMenu">
      <li
        class="menulist__item"
        :class="typeOfMenu"
        v-for="item in item"
        :key="item.id"
      >
        <router-link class="menulist__link" :class="typeOfMenu" :to="item.link"
          >{{ item.name }}
        </router-link>
        <span v-if="hasTotal" class="menulist__total" :class="typeOfMenu">{{
          item.total
        }}</span>
      </li>
      <slot name="end"></slot>
    </ul>
  </div>
</template>
<script>
export default {
  name: "MenuList",

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
    typeOfMenu: {
      type: String,
      default: "default",
      validator(v) {
        return ["default", "vertical", "mobile"].includes(v);
      },
    },

    hasFinder: {
      type: Boolean,
      default: false,
    },
  },
};
</script>