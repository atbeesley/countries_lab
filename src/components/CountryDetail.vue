<template lang="html">
  <div v-if="country">
    <h3> {{ country.name }}</h3>
    <h4> {{ country.capital }}</h4>
    <h4> {{ country.population }} </h4>
    <h4>The inhabitants are known as {{country.demonym}}s.</h4>  
    <img :src="`${country.flag}`"></v-img> 
  </div>
</template>

<script>
export default {
  name: "country-detail",
  props: ["country"]
}

</script>

<style lang="css" scoped>
</style>
