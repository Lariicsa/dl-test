<template>
  <div class="container__main">
    <HeaderVue>
      <MenuList :item="topMenu" />
    </HeaderVue>
    <div class="row">
      <GridVue
        columns="1fr 1fr 1fr"
        columnGap="1.6rem"
        columnRow="1.6rem"
        :breakPointTablet="breakPointTablet"
        colsForTablet="1fr 1fr 1fr"
        :breakPointMobile="breakPointMobile"
        colsForMobile="100%"
      >
        <CardImage v-for="item in cardsData" :item="item" :key="item.id" />
      </GridVue>
    </div>
  </div>
</template>

<script>
import CardImage from "@/components/CardImage";
import GridVue from "@/components/Grid";
import HeaderVue from "@/components/Header";
import MenuList from "@/components/MenuList";
import DATA from "../mockdata/index.js";
export default {
  name: "HomeView",

  components: {
    CardImage,
    GridVue,
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

      breakPointTablet: 1200,
      breakPointMobile: 860,
      cardsData: DATA.cardsData,
    };
  },
};
</script>
