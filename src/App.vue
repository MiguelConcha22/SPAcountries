<template>
  <v-app>
    <SearchBar
      v-bind:subregions="Subregion"
      v-on:filter="filterByRegion"
    />
    <v-content>
      <Countries
        v-bind:countries="filteredCountries.length > 0 ? filteredCountries : Country"
      />
    </v-content>
  </v-app>
</template>

<script>
import SearchBar from './components/SearchBar';
import Countries from './components/Countries';
import gql from 'graphql-tag';

export default {
  name: 'App',

  components: {
    SearchBar,
    Countries,
  },
  apollo: {
    Country: gql`
      query {
        Country {
          _id
          name
          nativeName
          subregion {
            name
          }
          currencies {
            name
            symbol
          }
          flag {
            svgFile
          }
        }
      }
    `,
    Subregion: gql`
      query {
        Subregion {
          name
        }
      }
    `,
  },

  data: () => ({
    filteredCountries: [],
  }),

  methods: {
    filterByRegion(selectedRegion){
      this.filteredCountries = this.Country.filter(country =>
        {
          if ('subregion' in country && country.subregion !== null) {
            if ('name' in country['subregion'] && country.subregion.name !== null){
              return country.subregion.name === selectedRegion;
            } else {
              return false;
            }
          } else {
            return false;
          }
        }
      );
    },
  },
};
</script>
