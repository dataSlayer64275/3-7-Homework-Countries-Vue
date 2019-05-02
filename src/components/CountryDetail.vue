<template lang="html">
  <div>
    <h3>{{selectedCountry.name}}</h3>
    <h3>{{selectedCountry.capital}}</h3>
    <h3>{{selectedCountry.population}}</h3>
  </div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['selected-country']
}
</script>

<style lang="css" scoped>
</style>
