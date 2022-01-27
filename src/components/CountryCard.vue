<template>
  <div style="background: olive">
    *title* {{ country.name }}
    Population {{ country.population }}
    Region {{ country.region }}
    Capital {{ country.capital }}

  </div>

</template>

<script>
export default {
  name: "CountryCard",
  props:{
    country: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>

</style>