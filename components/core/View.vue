<template>
  <v-row :class="mainRow">
    <v-col cols="12" md="2" :class="sideCols">
    <v-img :src="require('@/assets/l2f_tr.png')" :class="logo"></v-img>
      <div :class="nestedRows" class="grey leftFixed darken-4">
        <div>
          1 jfdsljf sdlkfjs dfksdjfdl jfjlksdjlfdkjsfjdlfj
        </div>
        <div>
          <base-update />
        </div>
        <div>
          3
        </div>
        <div>
          4
        </div>
        <div class="mt-16">
          5
        </div>
      </div>
    </v-col>
    <v-col cols="12" md="8" :class="middleCol">

      <welcome :class="nestedRows" />

      <recent-projects :class="nestedRows" />

      <services :class="nestedRows" />

      <about-me :class="nestedRows" />

      <BaseDialogue :class="nestedRows" />

      <get-in-touch :class="nestedRows" />
    </v-col>
    <v-col cols="12" md="2" :class="sideCols">
      <v-row :class="nestedRows" class="flex-column leftFixed grey darken-4">
        <v-col>
          <h5>Register Today!</h5>
          <v-form v-model="valid" id="side_form" ref="form" lazy-validation>
          <v-text-field
            v-model="firstname"
            :rules="nameRules"
            :counter="10"
            label="First name"
            outlined
            shaped
            required
          ></v-text-field>


          <v-text-field
            v-model="lastname"
            :rules="nameRules"
            :counter="10"
            label="Last name"
            outlined
            shaped
            required
          ></v-text-field>


          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            outlined
            shaped
            required
          ></v-text-field>

              <v-select
      v-model="select"
      :items="items"
      :rules="[v => !!v || 'Item is required']"
      label="Item"
      required
    ></v-select>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>
  </v-form>
        </v-col>
        
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
import defaultLayout from "~/assets/js/vuetify_classes/layouts/default_layout";
export default {
  name: "CoreView",
  data: () => ({
    sideCols: defaultLayout.sideCol,
    mainRow: defaultLayout.firstRow,
    nestedRows: defaultLayout.nestedRow,
    middleCol: defaultLayout.middleCol,
    items: [
      { title: "Home", icon: "mdi-view-dashboard" },
      { title: "About", icon: "mdi-forum" },
    ],
    valid: false,
    firstname: "",
    lastname: "",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => v.length <= 10 || "Name must be less than 10 characters",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+/.test(v) || "E-mail must be valid",
    ],
          select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ],
      checkbox: false,
  }),
      methods: {
      validate() {
        this.$refs.form.validate();
      },
      reset() {
        this.$refs.form.reset();
      },
      resetValidation() {
        this.$refs.form.resetValidation();
      },
    },
  computed: {
    logo() {
      if (
        this.$vuetify.breakpoint.smAndUp &&
        this.$vuetify.breakpoint.mdAndDown
      )
        return "logoFixedSmAndUp";
      else if (this.$vuetify.breakpoint.mdAndUp) return "logoFixedMdAndUp";
      else return "logoFixedXs";
    },

  },
};
</script>

<style scoped lang="scss">

.sideNotched {
  clip-path: polygon(15% 15%, 0 0, 0 100%, 15% 85%);
}

.leftFixed {
  height: 80%;
  position: fixed;
  width: 15%;
  top: 15%;
  padding: 1%;
  overflow-y: scroll;
  overflow-x: hidden;
}

.logoFixedXs {
  position: fixed;
  top: 4%;
  left: 3%;
  min-height: 100%;
  transform: rotate(-40deg);
  width: 32px;
}

.logoFixedSmAndUp {
  position: fixed;
  top: 3.5%;
  left: 3%;
  transform: rotate(-45deg);
  width: 50px;
}

.logoFixedMdAndUp {
  position: fixed;
  top: 2%;
  left: 3%;
  transform: rotate(-50deg);
  width: 90px;
}

#side_form {
  * {
    margin-top: 16px;
  }
}

</style>
