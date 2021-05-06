<template lang="html">
  <li>{{ country.name }}</li>
</template>

<script>
import {eventBus} from "../main.js";
import {counties} from "../App";

export default {
  name: 'list-item',
  props: ['country'],
  methods: {
    handleClick(){
      eventBus.$emit('country-selected', this.country);
      eventBus.$emit(buildLangugagesList);
    },
    buildLangugagesList(event){
      list='';
      for(language in languages){
        list.push(language[0].name+', ')
      }
      console.log(this.list);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
