<template>
  <div class="content-wrapper">
    <div class="header">
      <div class="header-title">
        Where in the world?
      </div>
    </div>
    <div class="body" :class="darkMode ? 'dark' : 'light'">
      <countries-layout />
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import CountriesLayout from "@/components/CountriesLayout.vue";

@Options({
  components: {
    CountriesLayout
  },
  data(){
    return{
      darkMode: false,
    }
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:ital,wght@0,600;0,800;1,300&display=swap');
#app {
  font-family: 'Nunito Sans', sans-serif;
}
.header-title{
  padding: 1em 3em;
  font-weight: 800;
  font-size: 1.5rem;
}
.body{
}
</style>
