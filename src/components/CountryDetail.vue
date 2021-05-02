<template lang="html">
  <div v-if="country" class="detailbox">
    <h3> {{ country.name }}</h3>
    <h4> {{ country.capital }}</h4>
    <h4> {{ country.population }} </h4>
    <h4 v-if="country.demonym">The inhabitants are known as {{country.demonym}}s.</h4>  
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
