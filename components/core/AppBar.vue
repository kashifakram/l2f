<template>
  <div
  >
  <v-app-bar
    class="clippedHeader"
    :class="appClasses"
    v-scroll="onScroll"
    :color="isFixed ? 'teal darken-2' : 'teal darken-4'"
    flat
    app
    elevate-on-scroll
    :height="appBarHeight"
    
  >
  <v-app-bar-nav-icon @click.stop="drawer = !drawer" v-if="$vuetify.breakpoint.smAndDown"></v-app-bar-nav-icon>
  
    <v-toolbar-title class="text-subtitle-1 text-sm-h6 font-weight-bold font-sm-weight-regular text-uppercase ml-n6
    
    ">
    lonley to family
    </v-toolbar-title>

    <v-spacer></v-spacer>
<a href="#">
<v-card v-if="$vuetify.breakpoint.smAndUp" flat min-height="50%">
  <v-card-title class="text-subtitle-1">
    Love and Beloved
  </v-card-title>
  <v-card-subtitle>
    Visit your families!
  </v-card-subtitle>
</v-card>
</a>
  </v-app-bar>
<v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-title>Foo</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Bar</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Fizz</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Buzz</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

  </div>

</template>
<script>
import defaultLayout from "~/assets/js/vuetify_classes/layouts/default_layout";

export default {
  name: "CoreAppBar",
  components: {},
  data: () => ({
    showLogo: false,
    isScrolling: false,
    appClasses: defaultLayout.appBar,
    drawer: false,
    group: null,
  }),
  methods: {
    onScroll() {
      const offset = window.pageYOffset;
      this.isScrolling = offset > 50;
      this.showLogo = offset > 200;
    },
  },
  computed: {
    isFixed() {
      return this.$vuetify.breakpoint.mdAndUp;
    },
    appBarHeight() {
      if (
        this.$vuetify.breakpoint.smAndUp &&
        this.$vuetify.breakpoint.mdAndDown
      )
        return 60;
      else if (this.$vuetify.breakpoint.mdAndUp) return 80;
      else return 35;
    },
  },
  watch: {
      group () {
        this.drawer = false
      },
    },
};
</script>
<style scoped>
.clippedHeaderSmAndUp {
  padding: 0 17%;
  clip-path: polygon(0% 0%, 17% 100%, 83% 100%, 100% 0%);
}
.clippedHeader {
  padding: 0 17%;
  clip-path: polygon(0% 0%, 17% 100%, 83% 100%, 100% 0%);
}
</style>