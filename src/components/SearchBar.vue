<template>
  <v-app-bar
    app
    color="primary"
    dark
    elevate-on-scroll
  >
    <v-app-bar-nav-icon></v-app-bar-nav-icon>

    <v-toolbar-title>Title</v-toolbar-title>

    <v-spacer></v-spacer>

    <v-btn icon>
      <v-icon>mdi-magnify</v-icon>
    </v-btn>

  </v-app-bar>
</template>

<script>
  export default {
    name: 'SearchBar',
  }
</script>
