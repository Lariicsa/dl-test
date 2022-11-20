<template>
  <button
    :class="`button__${buttonClass}`"
    :style="`margin:${margin};`"
    @click="click"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "ButtonView",

  props: {
    buttonClass: {
      type: String,
      default: "default",
      validator(v) {
        return ["default", "secondary", "dropdown"].includes(v);
      },
    },

    margin: {
      type: String,
      default: "0.8rem",
    },
  },

  methods: {
    click() {
      this.$emit("click");
    },
  },
};
</script>