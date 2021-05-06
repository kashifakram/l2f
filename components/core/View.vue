<template>
  <v-row :class="mainRow">
    <v-col cols="12" md="2" :class="sideCols">
    <v-img :src="require('@/assets/l2f_tr.png')" :class="logo"></v-img>

      <v-row :class="nestedRows" class="flex-column leftFixed grey darken-4">
        <v-col>
          1 jfdsljf sdlkfjs dfksdjfdl jfjlksdjlfdkjsfjdlfj
        </v-col>
        <v-col>
          2
        </v-col>
        <v-col>
          3
        </v-col>
        <v-col>
          4
        </v-col>
        <v-col>
          5
        </v-col>
      </v-row>
    </v-col>
    <v-col cols="12" md="8" :class="middleCol">

      <welcome :class="nestedRows" />

      <recent-projects :class="nestedRows" />

      <services :class="nestedRows" />

      <about-me :class="nestedRows" />

      <core-dialog :class="nestedRows" />

      <get-in-touch :class="nestedRows" />
    </v-col>
    <v-col cols="12" md="2" :class="sideCols">
      
    </v-col>
  </v-row>
</template>

<script>
import defaultLayout from "~/assets/js/vuetify_classes/layouts/default_layout";
export default {
  name: "CoreView",

  components: {
    AboutMe: () => import("@/components/AboutMe"),
    GetInTouch: () => import("@/components/GetInTouch"),
    RecentProjects: () => import("@/components/RecentProjects"),
    Services: () => import("@/components/Services"),
    Welcome: () => import("@/components/Welcome"),
    CoreDialog: () => import("@/components/base/Dialogue"),
    CoreMainMenu: () => import("@/components/core/MainMenu"),
    BaseCard: () => import("@/components/base/Card"),
    BaseCardTop: () => import("@/components/base/CardTop"),
  },
  data: () => ({
    sideCols: defaultLayout.sideCol,
    mainRow: defaultLayout.firstRow,
    nestedRows: defaultLayout.nestedRow,
    middleCol: defaultLayout.middleCol,
    items: [
      { title: "Home", icon: "mdi-view-dashboard" },
      { title: "About", icon: "mdi-forum" },
    ],
  }),
  computed: {
    logo() {
      if (this.$vuetify.breakpoint.smAndUp && this.$vuetify.breakpoint.mdAndDown) return "logoFixedSmAndUp";
      else if (this.$vuetify.breakpoint.mdAndUp ) return "logoFixedMdAndUp";
      else return "logoFixedXs";
    },
  },
};
</script>
<style scoped>
.sideNotched {
  clip-path: polygon(15% 15%, 0 0, 0 100%, 15% 85%);
}
.leftFixed {
  position: fixed;
  width: 15%;
  padding: 2%;
}
.logoFixedXs {
  position: fixed;
  top: 4%;
  left: 3%;
  transform: rotate(-40deg);
  width: 32px;
}
.logoFixedSmAndUp {
  position: fixed;
  top: 3.5%;
  left: 3%;
  transform: rotate(-45deg);
  width: 50px;
}
.logoFixedMdAndUp {
  position: fixed;
  top: 2%;
  left: 3%;
  transform: rotate(-50deg);
  width: 90px;
}


</style>
