<template>
  <v-btn
    color="secondary"
    class="clippedButton"
    v-bind="$attrs"
    v-on="$listeners"
    outlined
  >
    <slot />
  </v-btn>
</template>

<script>
  export default {
    name: 'BaseBtn',
  }
</script>

<style scoped>
  .clippedButton {
    padding: 0 4%;
    clip-path: polygon(0% 0%, 10% 100%, 90% 100%, 100% 0%);
    border: 3px solid greenyellow;
  }
</style>