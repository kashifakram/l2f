<template>
    <v-app dark>
    <core-system-bar />
    <core-app-bar />
    <Nuxt />
  </v-app>
</template>

<script>
export default {
    name: 'member',
  components: {
    CoreAppBar: () => import('@/components/core/AppBar'),
    CoreSystemBar: () => import('@/components/core/SystemBar'),
  }
}
</script>

<style>

</style>