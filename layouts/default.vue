<template>
  <v-app dark>
    <core-app-bar />
    <core-view />
    <v-footer
    class="clippedFooter"
      fixed
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  components: {
    CoreAppBar: () => import('@/components/core/AppBar'),
    CoreView: () => import('@/components/core/View'),

  }
}
</script>
<style>

</style>
