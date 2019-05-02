<template lang="html">
  <div>
    <ul>
      <list-item v-for="(country,index) in countries" :country="country" :key="index" ></list-item>
    </ul>
  </div>
</template>

<script>

// The reason we shouldn't componetize the options (in the way we have done above here) is because
// <option> is mandatory for <select>'s, whereas in a <ul> we can put pretty much anything.

import ListItem from './ListItem.vue';

export default {
  name: 'country-list',
  props: ['countries'],
  components: {
    'list-item' : ListItem
  },
}
</script>

<style lang="css" scoped>
</style>
