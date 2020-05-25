<template>
  <v-card
    class="mx-auto"
    max-width="300px"
  >
    <v-list>
      <v-toolbar
        color="black"
        dark
      >
        <v-spacer></v-spacer>
        <v-toolbar-title>Countries</v-toolbar-title>
        <v-spacer></v-spacer>
      </v-toolbar>
      <v-list-item
        three-line
        v-for="country in countries" :key="country._id"
      >
        <v-list-item-avatar>
          <v-img :src="country.flag.svgFile"></v-img>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>
            {{ country.name }}
          </v-list-item-title>
          <v-list-item-subtitle>
            {{ country.nativeName }}
          </v-list-item-subtitle>
          <v-list-item-subtitle>
            <v-chip
              color="secondary"
              x-small
              v-for="currency in country.currencies"
              :key="currency.name">
              {{ currency.name }} ({{currency.symbol}})
            </v-chip>
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-card>
</template>

<script>
  export default {
    name: 'Countries',
    props: ["countries"],

    data: () => ({
    }),
  }
</script>
