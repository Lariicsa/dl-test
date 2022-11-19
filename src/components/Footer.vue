<template>
  <footer class="footer">
    <div class="footer__top">
      <MenuList :item="footerTopMenu" />
    </div>
    <div class="footer__bottom">
      <div class="footer__bottom-group">
        <div class="col" v-html="firstFooterDetails"></div>
      </div>
      <div class="footer__bottom-group">
        <ul class="footer__menu">
          <li
            class="footer__menu-item"
            v-for="detail in secondFooterDetails"
            :key="detail.link"
          >
            <router-link class="footer__menu-link" :to="detail.link">{{ detail.name }}</router-link>
          </li>
        </ul>
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
      type: String,
    },
    secondFooterDetails: {
      type: Array,
    },
  },
};
</script>