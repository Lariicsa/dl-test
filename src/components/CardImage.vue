<template>
  <div class="cardimage">
    <div class="cardimage__image" :style="item.image">
      <span class="cardimage__quality">item.quality</span>
      <span class="cardimage__duration">item.duration</span>
    </div>
    <div class="cardimage__description">item.description</div>
    <div class="cardimage__tags">
      <div v-for="tag in tags" :key="tag.id" class="cardimage__tag">
        {{ tag.name }}
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