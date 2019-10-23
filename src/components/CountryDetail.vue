<template lang="html">
  <div v-if="country">
    <h3> {{ country.name }}</h3>
    <h4> {{ country.capital }}</h4>
    <h4> {{ country.population }} </h4>
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
