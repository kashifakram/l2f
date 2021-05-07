<template>
  <v-card :loading="loading">
      <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>
        <v-img
      height="250"
      src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
    ></v-img>
    <v-card-title>
        Update your families, what are you up to?
    </v-card-title>
    <v-card-subtitle>
        Inform Families!
    </v-card-subtitle>
    <v-card-text>
              <v-row
        align="center"
        class="mx-0"
      >
        <v-rating
          :value="4.5"
          color="amber"
          dense
          half-increments
          readonly
          size="14"
        ></v-rating>

        <div class="grey--text ml-4">
          4.5 (413)
        </div>
        <p>
        Let your families know your current situation, what you are doing and how's life going.</p>

      </v-row>
    </v-card-text>
        <v-divider class="mx-4"></v-divider>

    <v-card-title>Tonight's availability</v-card-title>

    <v-card-text>
      <v-chip-group
        v-model="selection"
        active-class="deep-purple accent-4 white--text"
        column
      >
        <v-chip>5:30PM</v-chip>

        <v-chip>7:30PM</v-chip>

        <v-chip>8:00PM</v-chip>

        <v-chip>9:00PM</v-chip>
      </v-chip-group>
    </v-card-text>
    <v-card-action>
        <v-btn color="deep-purple lighten-2"
        text
        @click="reserve">
            Update Now
        </v-btn>
    </v-card-action>
  </v-card>
</template>

<script>
export default {
    components: {
    },
    data: () => ({
        loading: false,
      selection: 1,
    }),
    methods: {
      reserve () {
        this.loading = true
        setTimeout(() => (this.loading = false), 2000)
      },
    },
}
</script>

<style>

</style>