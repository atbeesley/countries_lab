<template lang="html">
  <div v-if="country" class="detailbox">
    <h2>{{ country.name }}</h2>
    <p v-if="country.capital"> Capital: {{ country.capital }}</p>
    <p>Population: {{ country.population }} </p>
    <h3>Some tasty factoids about {{ country.name }}:</h3>
    <ul>
    <li v-if="country.region"><p v-if="country.region">It is located somewhere in the {{country.region}} region.</p></li>
    <li v-if="country.demonym"><p v-if="country.demonym">The inhabitants are known as {{country.demonym}}s.</p></li>
    <li  v-if="country.languages"><p v-if="country.languages">The locals parley in {{country.languages[0].name}}.</p></li>
    <!-- </li><p v-if="typeof country.regionalBlocs !== undefined">It belongs to the {{country.regionalBlocs[0].name}}.</p></li> -->
    </ul>
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
