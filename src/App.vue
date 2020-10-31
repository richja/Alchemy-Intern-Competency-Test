<template>
  <div id="app">
    <Main />
  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main
  }
}
</script>

<style>
#app {
  text-align: center;
  margin-top: 4%;
}

body {
  background-color: rgb(32, 32, 32);
}
</style>
