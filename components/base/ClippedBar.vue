<template>
  <v-sheet
  v-bind="$attrs"
  v-on="$listeners"
  :class="clippedClass"
  >
    <slot />
  </v-sheet>
</template>

<script>
export default {
    name: 'BaseClippedBar',
    props: {
        isTop: {
            required: false,
            type: Boolean,
            default: true,
        }
    },
    computed: {
        clippedClass: () => this.isTop ? "clippedTop" : "clippedBottom"
    }
}
</script>

<style scoped>
.clippedTop {
    padding: 0 10%;
    padding-left: 4%;
    clip-path: polygon(0% 0%, 10% 100%, 90% 100%, 100% 0%);
  }
.clippedBottom {
  padding: 0 10%;
  height: 10%;
  clip-path: polygon(0% 100%, 10% 0%, 90% 0%, 100% 100%);
}
</style>