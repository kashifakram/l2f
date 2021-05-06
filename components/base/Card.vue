<template>
  <v-card class="clipped elevation-12">

  </v-card>
</template>

<script>
export default {
    name: "BaseCard"

}
</script>

<style scoped>
    .clipped {
        background-color: cadetblue;
        width: 500px;
        height: 100px;
        clip-path: polygon(15% 15%, 0 0, 100% 0, 85% 15%, 85% 85%, 100% 100%, 0 100%, 15% 85%);
    }
</style>