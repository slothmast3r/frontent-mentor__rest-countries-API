<template>
  <div style="width: 100px; height: 100px; background: red">
    {{ country }}
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