<template>
  <div class="cardimage">
    <div
      class="cardimage__image"
      :style="`background-image: url(${item.image})`"
      :class="{ isnew: item.isNew }"
    >
      <span class="cardimage__quality">{{ item.quality }}</span>
      <span class="cardimage__duration">{{ item.duration }} min</span>
    </div>
    <div class="cardimage__description">{{ item.description }}</div>
    <div class="cardimage__tags">
      <div v-for="tag in item.tags" :key="tag" class="cardimage__tag">
        {{ tag }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "CardImage",

  props: {
    item: {
      type: Object,
    },
  },
};
</script>