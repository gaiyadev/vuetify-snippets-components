<template>
  <v-container>
    <v-alert type="success" border="top" elevation="3" color="red lighten-2">I'm a success alert</v-alert>
    <v-app-bar color="deep-purple accent-4" dense dark>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>Page title</v-toolbar-title>
      <v-spacer></v-spacer>
<v-card
    class=""
elevation=""
    max-width=""
  >
    <v-card-text>
      <p class="">
       
      </p>
      <div class="text--primary">
       
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        text
        color=""
      >
       
      </v-btn>
    </v-card-actions>
  </v-card>
      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>
    <v-btn small elevation color="primary">Primary</v-btn>
    <v-btn class="mx-2" fab dark color="indigo">
      <v-icon dark>mdi-plus</v-icon>
    </v-btn>
    <v-text-field
      type
      append-icon="mdi-heart"
      error-count
      placeholder
      label="Outlined"
      outlined
      color
    ></v-text-field>
vapp
    <v-select color v-model="item" :items="items" filled label="Filled style"></v-select>
    <v-textarea
      outlined
      color
      placeholder
      error-count
      name="input-7-4"
      label="Outlined textarea"
      value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
    ></v-textarea>

    <v-bottom-navigation grow color="teal">
      <v-btn>
        <span>Recents</span>
        <v-icon>mdi-history</v-icon>
      </v-btn>

      <v-btn>
        <span>Favorites</span>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn>
        <span>Nearby</span>
        <v-icon>mdi-map-marker</v-icon>
      </v-btn>
    </v-bottom-navigation>

    <v-combobox
      v-model="select"
      color
      label="Select a favorite activity or create a new one"
      multiple
    ></v-combobox>

    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn color="primary" dark v-bind="attrs" v-on="on">Dropdown</v-btn>
      </template>
      <v-list>
        <v-list-item v-for="(item, index) in items" :key="index">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>

    <template>
      <v-container fluid>
        <v-row class="text-center">
          <v-col cols="3" sm="2" md="3"></v-col>
          <v-col cols="12" sm="8" md="6">
            <v-card elevation="11" class="pt-10">
              <h2 class="purple--text text-uppercase animate__animated animate__flash">{{ title }}</h2>
              <v-divider color="purple" class="mt-2"></v-divider>
              <v-form
                @submit.prevent="onLogin"
                ref="form"
                v-model="valid"
                lazy-validation
                class="mt-10 mb-6 pr-8 pl-8 pb-8 pt-4"
              >
                <v-text-field
                  v-model="email"
                  append-icon="mail_outline"
                  outlined
                  color="purple"
                  error-count="2"
                  :rules="emailRules"
                  label="E-mail"
                  required
                ></v-text-field>
                <v-text-field
                  v-model="password"
                  color="purple"
                  :rules="passwordRules"
                  :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                  @click:append="show1 = !show1"
                  :type="show1 ? 'text' : 'password'"
                  label="Password"
                  outlined
                  required
                ></v-text-field>

                <v-btn
                  x-large
                  type="submit"
                  block
                  :disabled="!valid"
                  :loading="loading"
                  color="purple darken-4"
                  class="mr-4 text"
                  @click="validate"
                >
                  <span class="white--text">Login</span>
                  <v-icon light>cached</v-icon>
                </v-btn>
              </v-form>
            </v-card>
          </v-col>
          <v-col cols="3" sm="2" md="3"></v-col>
        </v-row>
      </v-container>
    </template>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    title: "Login",
    valid: true,
    show1: false,
    show2: false,
    email: "",
    emailRules: [
      v => !!v || "E-mail is required",
      v => /.+@.+\..+/.test(v) || "E-mail must be valid"
    ],
    password: "",
    passwordRules: [
      v => !!v || "Password is required",
      v => (v && v.length >= 8) || "Password must be less than 8 characters"
    ]
  }),

  methods: {
    //..validate inputs
    validate() {
      this.$refs.form.validate();
    },
    //... Login a user to the app
    onLogin() {
      //api call here
    }
  }
};
</script>

<style scoped>
</style>





















  </v-container>
</template>

