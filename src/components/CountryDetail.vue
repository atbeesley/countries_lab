<template lang="html">
  <div v-if="country" class="detailbox">
    <h2>{{ country.name }}</h2>
    <h4 v-if="country.capital"> Capital: {{ country.capital }}</h4>
    <h4>Population: {{ country.population }} </h4>
    <h3>Some tasty factoids about {{ country.name }}:</h3>
    <h4 v-if="country.region">It is located somewhere in the {{country.region}} region.</h4>
    <h4 v-if="country.demonym">The inhabitants are known as {{country.demonym}}s.</h4>  
    <h4 v-if="country.languages">The locals parley in {{country.languages[0].name}}.</h4>
    <!-- <h4 v-if="country.regionalBlocs[0]">It belongs to the {{country.regionalBlocs[0].name}}.</h4> -->
    <!-- <h4 v-if="country.regionalBlocs.size()>1">It is part of {{country.regionalBlocs[1]}}.</h4> -->
    <img 
    :src="`${country.flag}`"   
    :alt="`Flag of ${country.name}`"
    :class="flag"
    style="  
    max-width: 30em;
    max-height: 20em;"
    ></v-img> 
  </div>
</template>

<script>
export default {
  name: "country-detail",
  props: ["country"]
}

</script>

<style lang="css" scoped>
.detailbox{
  padding-top: 1em;
  margin-left: -500px;
}
</style>
