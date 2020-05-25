<template>
  <v-container>
    <v-list>
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
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-container>
</template>

<script>
  export default {
    name: 'Countries',

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
    }),
  }
</script>
