<template>
  <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="40%"
      overlay-color="transparent"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="red lighten-2"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Click Me
        </v-btn>
      </template>

<div class="clippedDialog blue darken-4">
        <div class="grey darken-4 text-center text-h6">
          Privacy Policy
        </div>
    <div class="dtext text-center">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
    </div>
    <div class="text-center"> 
        <div>
          <v-btn
            color="secondary"
            text
            @click="dialog = false"
          >
            I accept
          </v-btn>
        </div>
        </div>
      </div>
    </v-dialog>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        dialog: false,
      }
    },
  }
</script>

<style scoped>
  .clippedDialog {
    /* clip-path: polygon(0% 0%, 10% 100%, 90% 100%, 100% 0%); */
    clip-path: polygon(0 15%, 15% 0, 85% 0%, 100% 15%, 100% 85%, 85% 100%, 15% 100%, 0% 85%);
    border: 5px black solid;
  }

    .clippedDFooter {
        background-color: blueviolet;
    padding-left: 10%;
    clip-path: polygon(0% 100%, 10% 0%, 90% 0%, 100% 100%);
  }

  .dtext {
      width: 80%;
      margin: 0 auto;
  }

  .parentClipped {
      background-color: black;
      clip-path: polygon(15% 14%, 0 0, 100% 0, 85% 15%, 85% 85%, 100% 100%, 0 100%, 16% 85%);
  }
</style>