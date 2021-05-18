<template>
  <v-card class="clipped">

  </v-card>
</template>

<script>
export default {
    name: "BaseCardTop"
}
</script>

<style scoped>
    .clipped {
        background-color: cadetblue;
        width: 500px;
        height: 100px;
        clip-path: polygon(0 0, 15% 15%, 85% 15%, 100% 0, 99% 100%, 85% 85%, 15% 84%, 0 100%);
    }
</style>