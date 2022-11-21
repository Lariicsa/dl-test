<template>
  <div class="cardimage">
    <div
      class="cardimage__image"
      :style="`background-image: url(${
        item.image != undefined ? item.image : ''
      })`"
    >
      <span v-if="item.isNew" class="cardimage__ribbon">New</span>
      <div class="cardimage__play"></div>
      <span class="cardimage__quality">{{ item.quality }}</span>
      <span class="cardimage__duration">{{ item.duration }} min</span>
    </div>
    <div class="cardimage__description">{{ item.description }}</div>
    <div class="cardimage__tags">
      <TagVue v-for="tag in item.tags" :key="tag" :text="tag" />
    </div>
  </div>
</template>
<script>
import TagVue from "@/components/Tag";

export default {
  name: "CardImage",

  components: {
    TagVue,
  },

  props: {
    item: {
      type: Object,
    },
  },
};
</script>