<template lang="html">
  <div>
    <select @change="handleChange" v-model="selectedCountry">
      <option v-for="(country, index) in countries" :value="country" :key="index">
        {{ country.name }}
      </option>
    </select>
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
