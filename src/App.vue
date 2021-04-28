<template>
  <div id="app">
    <Header />
    <Getapi />
    <router-view/>
  </div>
</template>

<script>
import Header from './components/Header'
import Getapi from './components/Getapi'
export default {
  name: 'App',
  components: {Header, Getapi}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
 padding: 0;
 margin: 0;
}
 body{
        margin: 0px !important;
        padding: 0;
        width: 100%;
        height: 100%;
    }
</style>
