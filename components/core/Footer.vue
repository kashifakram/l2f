<template>
  <v-footer
    height="88"
    class="left-center clippedFooter"
    app
  >
    <social-media />
    <v-spacer />
      <span>&copy; {{ new Date().getFullYear() }}</span>

  </v-footer>
</template>

<script>
export default {
  name: "CoreFooter",

  components: {
    SocialMedia: () => import("@/components/SocialMedia"),
  },
};
</script>
<style scoped>
.clippedFooter {
  padding: 0 10%;
  height: 10%;
  clip-path: polygon(0% 100%, 10% 0%, 90% 0%, 100% 100%);
}
</style>
