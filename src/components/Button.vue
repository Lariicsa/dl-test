<template>
  <button
    class="button"
    :class="buttonClass"
    :style="`margin:${margin};`"
    @click="click"
  >

    <slot></slot>

    <IconView
      v-if="hasIcon"
      :iconName="hasIcon"
      :color="isText ? type : 'white'"
      :width="iconSize"
      :height="iconSize"
      margin="0 -0.5rem 0 0.8rem;"
    ></IconView>
  </button>
</template>

<script>
import IconView from "@/components/Icon";
import ICON_LIST from "@/data/iconList";

export default {
  name: "MonButton",

  components: { IconView },

  props: {
    type: {
      type: String,
      default: "default",
      validator(v) {
        return [
          "default",
          "primary",
        ].includes(v);
      },
    },


    hasIcon: {
      type: String,
      validator(v) {
        return ICON_LIST.icons.includes(v);
      },
    },
    size: {
      type: String,
      default: "md",
      validator(v) {
        return ["xs", "sm", "md", "lg", "xl"].includes(v);
      },
    },
    margin: {
      type: String,
      default: "0.4rem",
    },
  },

  methods: {
    click() {
      if (!this.isDisabled && !this.isLoading) {
        this.$emit("click");
      }
    },
  },

  computed: {
    buttonClass() {
      return `${this.type} ${this.isText ? "text" : ""} ${
        this.isLink ? "link" : ""
      } ${this.isDisabled ? "disabled" : ""} ${
        this.isBlock ? "full-width" : ""
      } ${this.size} ${this.isLoading ? "loading" : ""} ${
        this.isBlock ? "block" : ""
      }`;
    },

    iconSize() {
      switch (this.size) {
        case "xs":
          return "1.2rem";
        case "sm":
          return "1.6rem";
        case "md":
          return "1.8rem";
        case "lg":
          return "2rem";
        default:
          return "2.2rem";
      }
    },
  },
};
</script>