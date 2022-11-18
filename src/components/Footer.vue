<template>
  <footer class="footer">
    <div class="footer__top">
      <MenuList :item="footerTopMenu" />
    </div>
    <div class="footer__bottom">
      <div class="footer__bottom-group">
        <div
          class="col"
          v-for="detail in firstFooterDetails"
          v-html="detail"
          :key="detail.slug"
        ></div>
      </div>
      <div class="footer__bottom-group">
        <div
          class="col"
          v-for="detail in secondFooterDetails"
          v-html="detail"
          :key="detail.slug"
        ></div>
      </div>
      <div class="footer__bottom-group">
        <slot></slot>
      </div>
    </div>
  </footer>
</template>
<script>
import MenuList from "@/components/MenuList";
export default {
  name: "FooterView",

  components: {
    MenuList,
  },

  props: {
    footerTopMenu: {
      type: Array,
    },
    firstFooterDetails: {
      type: Array,
    },
    secondFooterDetails: {
      type: Array,
    },
  },
};
</script>