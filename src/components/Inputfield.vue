<template>
  <div class="inputfield" :style="`margin: ${margin}`">
    <div class="inputfield__title" v-if="titleLabel">{{ titleLabel }}</div>

    <div class="inputfield__inner">
      <input
        :name="inputName"
        :type="type"
        :disabled="disabled"
        :class="
          showError ? 'inputfield__input error' : 'inputfield__input hide'
        "
        :placeholder="placeholder"
        ref="input"
        :value="value"
        @input="updateValue()"
        @keyup="keyup()"
        @keyup.enter="keyupEnter()"
        @blur="blur()"
        :maxlength="maxlength"
      />
      <span class="inputfield__icon"> </span>
    </div>
  </div>
</template>
<script>
/* eslint-disable */

export default {
  name: "InputField",

  props: {
    titleLabel: {
      type: String,
    },
    placeholder: {
      type: String,
    },
    inputType: {
      type: String,
      validator(v) {
        return [
          "text",
          "tel",
          "number",
          "password",
          "email",
          "date",
          "hidden",
        ].includes(v);
      },
    },

    value: {
      type: [String, Number],
      default: "",
    },
    inputName: {
      type: String,
      default: undefined,
    },
    autofocus: {
      type: Boolean,
      default: false,
    },

    placeholderText: {
      type: String,
      default: undefined,
    },
    margin: {
      type: String,
      default: "1.6rem auto",
    },
  },

  mounted() {
    if (this.autofocus) this.$refs.input.focus();
  },
  methods: {
    updateValue() {
      const VALUE =
        this.type === "number"
          ? parseFloat(this.$refs.input.value)
          : this.$refs.input.value;
      this.$emit("input", VALUE);
    },
    keyup() {
      this.$emit("keyup");
    },
    keyupEnter() {
      this.$emit("keyupEnter");
    },
    blur() {
      this.$emit("blur");
    },
    eyeClick() {
      const DEFAULT = this.type === "password";
      if (DEFAULT) {
        this.type = "text";
        this.displayedIcon = "eye";
        this.iconColor = "dark-2";
      } else {
        this.type = "password";
        this.displayedIcon = "eye-off";
        this.iconColor = "dark-4";
      }
    },
  },
};
</script>
