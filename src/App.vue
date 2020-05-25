<template>
  <v-app>
    <SearchBar v-on:filter="filterByRegion"/>
    <v-content>
      <Countries
        v-bind:countries="filteredCountries.length > 0 ? filteredCountries : countries"
      />
    </v-content>
  </v-app>
</template>

<script>
import SearchBar from './components/SearchBar';
import Countries from './components/Countries';

export default {
  name: 'App',

  components: {
    SearchBar,
    Countries,
  },

  data: () => ({
    countries: [
      {
        _id: 3,
        name: 'Afghanistan',
        nativeName: 'افغانستان',
        subregion: {
          name: 'Southern Asia',
          region: {
            name: 'Asia',
          },
        },
        currencies: [
          {
            name: 'Afghan afghani',
            symbol: '؋',
          },
        ],
        flag: {
          emoji: '🇦🇫',
          emojiUnicode: 'U+1F1E6 U+1F1EB',
          svgFile: 'https://restcountries.eu/data/afg.svg',
        },
      },
      {
        _id: 27,
        name: 'Åland Islands',
        nativeName: 'Åland',
        subregion: {
          name: 'Northern Europe',
          region: {
            name: 'Europe',
          },
        },
        currencies: [
          {
            name: 'Euro',
            symbol: '€',
          },
        ],
        flag: {
          emoji: '🇦🇽',
          emojiUnicode: 'U+1F1E6 U+1F1FD',
          svgFile: 'https://restcountries.eu/data/ala.svg',
        },
      },
      {
        _id: 51,
        name: 'Albania',
        nativeName: 'Shqipëria',
        subregion: {
          name: 'Southern Europe',
          region: {
            name: 'Europe',
          },
        },
        currencies: [
          {
            name: 'Albanian lek',
            symbol: 'L',
          },
        ],
        flag: {
          emoji: '🇦🇱',
          emojiUnicode: 'U+1F1E6 U+1F1F1',
          svgFile: 'https://restcountries.eu/data/alb.svg',
        },
      },
    ],
    filteredCountries: [],
  }),

  methods: {
    filterByRegion(selectedRegion){
      this.filteredCountries = this.countries.filter(
        country => country.subregion.name === selectedRegion
      );
    },
  },
};
</script>
