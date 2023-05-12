<template>
  <div id="home-page">
    <Landing></Landing>
    <Welcome></Welcome>
    <About></About>
    <Featured></Featured>
  </div>
</template>

<style lang="scss">
  @media screen and (min-width: 0px) {
    #home-page {
      display: flex;
      flex-direction: column;
      gap: 15rem;
    }
  }
  @media screen and (min-width: 768px) {
    #home-page {
      gap: 10rem;
    }
  }
  @media screen and (min-width: 1440px) {
    #home-page {
      gap: 15rem;;
    }
  }
</style>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage'
})
</script>
