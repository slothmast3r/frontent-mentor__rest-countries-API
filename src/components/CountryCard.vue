<template>
  <div class="card-wrapper">
    <img :src="country.flags.svg" class="flag-svg" :alt="'Flag: ' + country.name">
    <div class="title">
    {{ country.name }}
    </div>
    <div>
    Population {{ country.population }}
    </div>
    <div>
    Region {{ country.region }}
    </div>
    <div>
    Capital {{ country.capital }}
    </div>

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

<style scoped lang="scss">
@import "styles/_variables.scss";
.card-wrapper{
  font-size: 1rem;
  display: flex;
  flex-direction: column;
  border-radius: 0.5em;
  background: $veryLightGray-lightMode;

  width: 16em;
  .title{
    font-size: 1.25em;
    font-weight: 800;
  }
  .flag-svg{
    width: 16em;
    border-radius: 0.5em 0.5em 0 0;
  }
}
</style>