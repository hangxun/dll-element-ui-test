<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/>
    <hr>
    <MixinTest/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import MixinTest from 'mixintest'

export default {
  name: 'app',
  components: {
    HelloWorld,
    MixinTest
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
