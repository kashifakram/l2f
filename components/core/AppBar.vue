<template>
  <v-app-bar
    class="clippedHeader"
    :class="appClasses"
    elevation=24
    v-scroll="onScroll"
    :color="isFixed ? 'teal darken-2' : 'teal darken-4'"
    flat
    app
  >

  <v-app-bar-nav-icon v-if="$vuetify.breakpoint.smAndDown"></v-app-bar-nav-icon>
  <template v-slot:img="{ props }">
      <v-img
        v-bind="props"
        contain
        height="50"

      />
  </template>

    <v-app-bar-title class="text-h6">lonely->family</v-app-bar-title>

    <v-spacer />

    <base-btn
      href="https://store.vuetifyjs.com/product/freelancer-theme-free?ref=freelancer"
      class="text-caption"
    >
      Download for Free

      <v-icon
        right
        small
      >
        mdi-open-in-new
      </v-icon>
    </base-btn>
  </v-app-bar>
</template>
<script>
import defaultLayout from "~/assets/js/vuetify_classes/layouts/default_layout";

export default {
  name: "CoreAppBar",
  components: {
  },
  data: () => ({
    showLogo: false,
    isScrolling: false,
    appClasses: defaultLayout.appBar,
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
  },
};
</script>
<style scoped>
.clippedHeader {
  padding: 0 17%;
  clip-path: polygon(0% 0%, 17% 100%, 83% 100%, 100% 0%);
}

</style>