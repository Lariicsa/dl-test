<template>
  <div class="container__out">
    <HeaderVue>
      <MenuList :item="topMenu">
        <template v-slot:end>
          <ButtonVue buttonClass="default">SYNC NOW</ButtonVue>
        </template></MenuList
      >

      <MenuList
        :style="`display:${isOpenMenu ? 'flex' : 'none'}`"
        :item="formattedPositions"
        typeOfMenu="mobile"
        :hasTotal="true"
        :hasFinder="true"
      >
        <template v-slot:finder>
          <InputField placeholder="Search positions"></InputField>
        </template>
      </MenuList>
    </HeaderVue>
    <div class="container__main">
      <div class="sidebar">
        <MenuList
          :item="formattedPositions"
          typeOfMenu="vertical"
          :hasTotal="true"
        />
      </div>

      <div class="container__inner">
        <div class="row positions">
          <ButtonVue buttonClass="dropdown" @click="openPositionsMenu"
            >Positions</ButtonVue
          >
        </div>
        <div class="row">
          <h2>Latest updates</h2>
          <GridVue
            columns="1fr 1fr 1fr"
            columnGap="1.6rem"
            columnRow="5.6rem"
            :breakPointTablet="breakPointTablet"
            colsForTablet="1fr 1fr"
            :breakPointMobile="breakPointMobile"
            colsForMobile="100%"
            margin="0"
          >
            <CardImage v-for="item in cardsData" :item="item" :key="item.id" />
          </GridVue>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/*eslint-disable */
import ButtonVue from "@/components/Button";
import CardImage from "@/components/CardImage";
import InputField from "@/components/Inputfield";
import GridVue from "@/components/Grid";
import HeaderVue from "@/components/Header";
import MenuList from "@/components/MenuList";
import DATA from "../mockdata/index.js";
export default {
  name: "HomeView",

  components: {
    ButtonVue,
    CardImage,
    InputField,
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

      breakPointTablet: 1280,
      breakPointMobile: 1024,
      cardsData: DATA.cardsData,
      positions: DATA.positionsData,
      isOpenMenu: false,
    };
  },

  methods: {
    openPositionsMenu() {
      this.isOpenMenu = !this.isOpenMenu;
    },
  },

  computed: {
    formattedPositions() {
      const ALL = this.positions.map((ele) => {
        return { ...ele, total: `(${ele.total})` };
      });
      return ALL;
    },
  },
};
</script>
