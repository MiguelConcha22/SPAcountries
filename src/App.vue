<template>
  <v-app>
    <SearchBar/>
    <v-content>
      <Countries/>
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
    //
  }),
};
</script>
