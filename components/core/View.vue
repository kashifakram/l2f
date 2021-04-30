<template>
  <div class="middle">
    <welcome />

    <recent-projects />

    <services />

    <about-me />

    <get-in-touch />
  </div>
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
