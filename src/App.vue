<template>
  <div id="app">
    <Header></Header>
    <card></card>
  </div>
</template>

<script>
import Header from './components/Header.vue'

import Card from './components/Card.vue'
export default {
  name: 'App',
  components: {
    Header,
    Card
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

</style>


