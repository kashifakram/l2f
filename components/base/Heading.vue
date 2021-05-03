<template>
  <component
    :is="tag"
    class="text-h4 v-heading mb-3 font-weight-light"
  >
    <slot />
  </component>
</template>

<script>
  export default {
    name: 'BaseHeading',

    props: {
      tag: {
        type: String,
        default: 'h4',
      },
    },
  }
</script>

<style lang="scss">
@import '~assets/sass/main';
  .v-heading {
    letter-spacing: 3px !important;
  }
</style>
