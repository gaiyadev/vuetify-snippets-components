<template>
  <v-container>
    <v-alert type="success" border="top" elevation="3" color="red lighten-2">I'm a success alert</v-alert>
    <v-app-bar color="deep-purple accent-4" dense dark>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Page title</v-toolbar-title>

      <v-spacer></v-spacer>

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

    <v-bottom-navigation   grow color="teal">
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

        <v-icon color="red" filled>fas fa-lock</v-icon>

  </v-container>
</template>

