<template>
  <v-sheet
    class="left-center clippedMenu"
    height="80"
    color="purple"
  >
    <social-media />
    <v-spacer />
      <span>&copy; {{ new Date().getFullYear() }}</span>

  </v-sheet>
</template>

<script>
export default {
  name: "CoreMainMenu",

  components: {
    SocialMedia: () => import("@/components/SocialMedia"),
  },
};
</script>
<style scoped>
.clippedMenu {
  padding: 0 10%;
  clip-path: polygon(0% 100%, 10% 0%, 90% 0%, 100% 100%);
}
</style>