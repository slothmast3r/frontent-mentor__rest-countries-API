<link rel="stylesheet" href="../../styles/_variables.scss">
<template>
  <div>
    <country-card
        v-for="country in countryRepositories"
        :country="country"
        :key="country.numericCode">
    </country-card>
  </div>
</template>

<script>

import {onMounted, ref, watch} from "vue";
import { fetchAllCountriesRepository } from "../../scripts/repositories";
import CountryCard from "@/components/CountryCard";
import { setup } from 'vue-class-component'

export default {
  name: "CountriesLayout",
  components: { CountryCard },
  data(){
    return{
      countryRepositories: [],
    }
  },
  async created() {
    await this.getCountryRepositories()
  },
  methods:{
    async getCountryRepositories() {
      this.countryRepositories = await fetchAllCountriesRepository()
    }
  },
  // #TODO LEARN HOW TO SETUP
  // async setup() {
  //
  //   const countryRepositories = ref([])
  //   const getCountryRepositories = async () => {
  //     countryRepositories.value = await fetchAllCountriesRepository()
  //   }
  //   await getCountryRepositories()
  //   watch(countryRepositories, (newValue)=>{
  //     countryRepositories.value = newValue
  //   })
  //   console.log('cycki')
  //   return { countryRepositories, getCountryRepositories }
  // }
}
</script>

<style scoped>

</style>