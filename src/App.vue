<template>
  <div class="space" id="app">
    <router-view />
    <FooterVue
      :footerTopMenu="footerMenu"
      :firstFooterDetails="firstFooterDetails"
      :secondFooterDetails="secondFooterDetails"
    >
      <ButtonVue buttonClass="secondary" margin="auto">SYNC NOW</ButtonVue>
    </FooterVue>
  </div>
</template>
<script>
import ButtonVue from "./components/Button";
import FooterVue from "@/components/Footer";

export default {
  name: "App",

  components: {
    ButtonVue,
    FooterVue,
  },

  data() {
    return {
      footerMenu: [
        { name: "home", link: "#" },
        { name: "her", link: "#" },
        { name: "position", link: "#" },
        { name: "devices", link: "#" },
        { name: "faqs", link: "#" },
        { name: "news", link: "#" },
        { name: "ig", link: "#" },
        { name: "fb", link: "#" },
      ],

      secondFooterDetails: [
        { name: "Contact Support", link: "#" },
        { name: "Epoch.com", link: "http://epoch.com" },
        { name: "Segpay.com", link: "http://Segpay.com" },
        { name: "Complyance with Mastercard Standards", link: "#" },
      ],
    };
  },

  computed: {
    firstFooterDetails() {
      return `
      <div class="footer__text">
        © 2022 La Touraine, Inc.
       <a href="#">18 USC 2257 Record-Keeping Requirements Compliance Statement</a>
       <div class="row between"><a href="#">Provacy Policy</a> |  <a href="#">Terms of Servce</a></div>
       <img src="assets/logo-rta.png"  class="footer__logo"/></div>
       `;
    },
  },
};
</script>

