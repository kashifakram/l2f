<template>
  <v-app dark>
    <core-system-bar />
    <core-app-bar />
    <core-view />
    <core-footer />
  </v-app>
</template>

<script>
export default {
  components: {
    CoreAppBar: () => import('@/components/core/AppBar'),
    CoreView: () => import('@/components/core/View'),
    CoreSystemBar: () => import('@/components/core/SystemBar'),
    CoreFooter: () => import('@/components/core/Footer'),

  }
}
</script>
<style>

</style>
