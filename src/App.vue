<template>
  <div id="app">
    <Pokedex msg="Pokédex"/>
  </div>
</template>

<script>
import Pokedex from './components/Pokedex.vue'

export default {
  name: 'app',
  components: {
    Pokedex
  }
}
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-image: linear-gradient(135deg, #c5d6fb 0%,#c1face 69%,#bdfbc0 100%);
  height: 100vh;
  overflow: auto;
  margin: 0;
  padding: 30px;
}
</style>
