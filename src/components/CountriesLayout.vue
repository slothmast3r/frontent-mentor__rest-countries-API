<template>
  <div>
    {{ countryRepositories}}
    <country-card
        v-for="country in countryRepositories"
        :country="country"
        :key="country.numericCode">
    </country-card>
  </div>
</template>

<script>

import {onMounted, reactive, ref} from "vue";
import { fetchAllCountriesRepository } from "../../scripts/repositories";
import CountryCard from "@/components/CountryCard";

export default {
  name: "CountriesLayout",
  components: { CountryCard },
  async setup() {

    const countryRepositories = ref([])
    const getCountryRepositories = async () => {
      countryRepositories.value = await fetchAllCountriesRepository()
    }
    onMounted(getCountryRepositories)
    return { countryRepositories, getCountryRepositories } // anything returned here will be available for the rest of the component
  }
}
</script>

<style scoped>

</style>