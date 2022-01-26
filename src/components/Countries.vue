<template>
  <div>

  </div>
</template>

<script>

import { ref } from "vue";
import { fetchAllCountriesRepository } from "../../scripts/repositories";

export default {
  name: "Countries",
  async setup() {

    const repositories = ref([])
    const getUserRepositories = async () => {
      repositories.value = await fetchAllCountriesRepository()
    }
    await getUserRepositories()

    return { getUserRepositories } // anything returned here will be available for the rest of the component
  }
}
</script>

<style scoped>

</style>