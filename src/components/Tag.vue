<template>
  <div class="tag">
    {{ text }}
  </div>
</template>
<script>
export default {
  name: "TagVue",

  props: {
    text: {
      type: String,
    },
  },
};
</script>