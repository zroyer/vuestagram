<template>
  <div id="app">
    <img src="./assets/logo.png">
    <Header msg="Made with Vue.js!"/>
    <InstaFeed />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import InstaFeed from './components/InstaFeed.vue'

export default {
  name: 'app',
  components: {
    Header,
    InstaFeed
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
