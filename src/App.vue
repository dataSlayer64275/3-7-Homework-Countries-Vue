<template lang="html">
  <div class="">
    <h1>Countries</h1>
    <div class="main container">
      <country-list :countries="countries"></country-list>
      <country-detail :selectedCountry="selectedCountry"></country-detail>
    </div>
  </div>
</template>

<script>

import {eventBus} from './main.js'
import CountryList from './components/CountryList.vue';
import CountryDetail from './components/CountryDetail.vue';

export default {
  name: 'app',
  data() {
    return {
      countries: [],
      // Set this to be null if passing in an entire object, this allows us to use v-if to render.
      selectedCountry: null
    };
  },
  components: {
    CountryList,
    CountryDetail
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries);


    // 2 arguments, name of event from $emit and callback which uses $emit object
    eventBus.$on('country-selected', (country) =>{
      this.selectedCountry = country
    })
  },
}
</script>

<style lang="css" scoped>
</style>
