<template>
  <v-btn
    :color = "out ? 'primary' : 'secondary'"
    class="clippedButton"
    v-bind="$attrs"
    v-on="$listeners"
    :outlined = "out"
  >
    <slot />
  </v-btn>
</template>

<script>
  export default {
    name: 'BaseBtn',
    props: {
      out: {
        required: false,
        type: Boolean,
        default: true
      }
    }
  }
</script>

<style scoped>
  .clippedButton {
    padding: 0 4%;
    clip-path: polygon(0% 0%, 10% 100%, 90% 100%, 100% 0%);
  }
</style>