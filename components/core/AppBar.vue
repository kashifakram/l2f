<template>
  <v-app-bar
    class="clippedHeader"
    v-scroll="onScroll"
    :color="!isScrolling ? 'blue' : 'lightgrey'"
    fixed
    flat
  >
    <v-slide-x-transition>
      <v-img
        v-if="showLogo"
        :src="require('@/assets/logo.png')"
        class="shrink"
        height="55"
        contain
      />
    </v-slide-x-transition>

    <v-spacer />

    <social-media />

    <base-btn
      class="ml-3"
      large
      href="https://store.vuetifyjs.com/product/freelancer-theme-free?ref=freelancer"
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
  export default {
    name: 'CoreAppBar',
    components: {
      SocialMedia: () => import('@/components/SocialMedia'),
    },
    data: () => ({
      showLogo: false,
      isScrolling: false,
    }),
    methods: {
      onScroll () {
        const offset = window.pageYOffset
        this.isScrolling = offset > 50
        this.showLogo = offset > 200
      },
    },
  }
</script>
<style>
  .clippedHeader {
    padding: 0 10%;
    padding-left: 4%;
    height: 5%;
    clip-path: polygon(0% 0%, 10% 100%, 90% 100%, 100% 0%);
  }
    .clippedFooter {
    padding-left: 10%;
    height: 10%;
    clip-path: polygon(0% 100%, 10% 0%, 90% 0%, 100% 100%);
  }
</style>