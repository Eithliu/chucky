<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/chucky.png" class="my-logo">
    <HelloWorld msg="Chucky - Les citations"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
@media (min-width: 1024px) {
  img.my-logo {
    width: 30%
  }
}
@media (max-width: 768px) {
  img.my-logo {
    width: 50%
  }
}
</style>
