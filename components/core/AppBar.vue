<template>
  <v-app-bar
    class="clippedHeader"
    height="80"
    v-scroll="onScroll"
    :color="!isScrolling ? 'blue' : 'lightgrey'"
    fixed
    flat
    app
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
<style scoped>
  .clippedHeader {
    padding: 0 10%;
    padding-left: 4%;
    clip-path: polygon(0% 0%, 10% 100%, 90% 100%, 100% 0%);
  }
</style>