<template>
  <footer class="footer">
    <div class="footer__top">
      <ul class="footer__topmenu">
        <li
          class="footer__item"
          v-for="(link, i) in footerTopMenu"
          :class="isNet(link.name)"
          :key="i * 0.34"
        >
          <router-link class="footer__link" :to="link.link">
            {{ showName(link.name) }}
          </router-link>
        </li>
      </ul>
    </div>
    <div class="footer__bottom">
      <div class="footer__bottom-group first">
        <div class="footer__simple" v-html="firstFooterDetails"></div>
      </div>
      <div class="footer__bottom-group second">
        <ul class="footer__menu">
          <li
            class="footer__menu-item"
            v-for="(detail, $ix) in secondFooterDetails"
            :key="$ix"
          >
            <router-link class="footer__menu-link" :to="detail.link">{{
              detail.name
            }}</router-link>
          </li>
        </ul>
      </div>
      <div class="footer__bottom-group third">
        <slot></slot>
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  name: "FooterView",

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

  computed: {
    isNet() {
      return (type) => {
        if (type === "fb" || type === "ig") {
          return `net ${type} `;
        }
      };
    },

    showName() {
      return (type) => {
        if (type === "fb" || type === "ig") {
          return "";
        } else {
          return type;
        }
      };
    },
  },
};
</script>