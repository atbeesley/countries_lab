<template lang="html">
  <div>
    <select @change="handleChange" v-model="selectedCountry">
      <option value="" disabled selected>Select a country</option>
      <option v-for="(country, index) in countries" :value="country" :key="index">
        {{ country.name }}
      </option>
    </select>
      <h3 v-if="!selectedCountry">Pick a country to learn about...</h3> 
  </div>
</template>

<script>
import ListItem from './ListItem.vue';
import {eventBus} from '../main.js'

export default {
  name: 'countries-list',
  props: ['countries'],
  data: function() {
    return {
      selectedCountry: null
    }
  },
  components: {
    "list-item": ListItem
  },

  methods: {
    handleChange(){
      eventBus.$emit('country-selected', this.selectedCountry)
    }
  }

}
</script>

<style lang="css" scoped>
</style>
