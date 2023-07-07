<template>
  <div id="app">
    <Pokemones/>
    <div>

    </div>
  </div>
</template>

<script>
import Pokemones from '@/components/Pokemones.vue'


export default {
  name: 'App',
  components: {
    Pokemones
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
