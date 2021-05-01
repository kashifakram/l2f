<template>
    <v-main app>
      <core-main-menu />
    <welcome />

    <recent-projects />

    <services />

    <about-me />

    <core-dialog />

    <get-in-touch />
    </v-main>
</template>

<script>
  export default {
    name: 'CoreView',

    components: {
      AboutMe: () => import('@/components/AboutMe'),
      GetInTouch: () => import('@/components/GetInTouch'),
      RecentProjects: () => import('@/components/RecentProjects'),
      Services: () => import('@/components/Services'),
      Welcome: () => import('@/components/Welcome'),
      CoreDialog: () => import('@/components/base/Dialogue'),
      CoreMainMenu: () => import('@/components/core/MainMenu'),

    },
  }
</script>
<style scoped>
  .middle {
    width: 80%;
    margin: 0 auto;
    margin-top: 3%;
    margin-bottom: 5%;
  }
</style>
