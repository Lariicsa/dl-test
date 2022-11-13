<template>
  <div class="container__main">
    <HeaderVue>
      <MenuList :item="topMenu" />
    </HeaderVue>
  </div>
</template>

<script>
import HeaderVue from "@/components/Header.vue";
import MenuList from "@/components/MenuList.vue";
export default {
  name: "HomeView",

  components: {
    HeaderVue,
    MenuList,
  },

  data() {
    return {
      topMenu: [
        { name: "her", link: "#" },
        { name: "position", link: "#" },
        { name: "devices", link: "#" },
        { name: "faqs", link: "#" },
      ],
    };
  },
};
</script>
