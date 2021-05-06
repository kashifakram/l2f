<template>
  <v-app dark>
    <core-system-bar />
    <core-app-bar />
  <v-main app>
    <Nuxt />
  </v-main>
  </v-app>
</template>

<script>
export default {
  components: {
    CoreAppBar: () => import('@/components/core/AppBar'),
    CoreSystemBar: () => import('@/components/core/SystemBar'),
    CoreFooter: () => import('@/components/core/Footer'),
  }
}
</script>
<style scoped>

</style>
