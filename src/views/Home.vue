<template>
  <main class="home">
    <h1>Welkom bij Beau-tique</h1>
    <h2>Ontdek onze producten en leer meer over ons.</h2>
  </main>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    
  }
}
</script>

<style scoped>
  .home {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 5rem 3rem;
  }

  h1 {
    font-size: 7rem;
    color: #40b782;
  }

  h2 {
    font-size: 3rem;
    color: black;
  }
</style>
