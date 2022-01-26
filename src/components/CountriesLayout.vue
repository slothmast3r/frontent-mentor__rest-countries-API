<template>
  <div>
    <country-card v-for="country in countriesRepository" :key="country.numericCode"/>
  </div>
</template>

<script>

import { ref } from "vue";
import { fetchAllCountriesRepository } from "../../scripts/repositories";
import CountryCard from "@/components/CountryCard";

export default {
  name: "Countries",
  components: {CountryCard},
  async setup() {

    const countriesRepository = ref([])
    const getCountriesRepository = async () => {
      countriesRepository.value = await fetchAllCountriesRepository()
    }
    await getCountriesRepository()
    console.log(countriesRepository)
    return { countriesRepository, getCountriesRepository } // anything returned here will be available for the rest of the component
  }
}
</script>

<style scoped>

</style>