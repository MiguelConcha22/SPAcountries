<template>
  <v-app-bar
    app
    color="primary"
    dark
    elevate-on-scroll
  >
    <v-toolbar-title>DeepLegal Demo</v-toolbar-title>

    <v-spacer></v-spacer>

    <v-container
      style="max-width: 200px;"
    >
      <v-autocomplete
        class="mt-6"
        :items="subregions"
        :filter="customFilter"
        color="white"
        item-text="name"
        label="Subregion"
        @change="(event) => selectRegion(event)"
      >
      </v-autocomplete>
    </v-container>
    <v-btn
      @click="$emit('filter', selectedRegion)"
      icon
    >
      <v-icon>mdi-magnify</v-icon>
    </v-btn>

  </v-app-bar>
</template>

<script>
  export default {
    name: 'SearchBar',
    props: ["subregions"],

    data: () => ({
      selectedRegion: '',
    }),

    methods: {
      customFilter (item, queryText) {
        const textOne = item.name.toLowerCase()
        const searchText = queryText.toLowerCase()

        return textOne.indexOf(searchText) > -1
      },
      selectRegion (event) {
        this.selectedRegion = event
      },
    },
  }
</script>
