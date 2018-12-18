<template>
  <div id="app">
    <app-header/>
    <router-view/>
  </div>
</template>

<script>
import AppHeader from './layouts/AppHeader.vue'

export default {
  components: {
    AppHeader
  }
}
</script>


<style>
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  html {
    font: 62.5% 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }

  body {
    font-size: 1.6rem;
  }

  a {
    text-decoration: none;
    color: inherit;
  }
</style>
