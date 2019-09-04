<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <Header/>
    <MainBody/>
  </div>
</template>

<script>
import Header from './components/Header/Header'
import MainBody from './components/MainBody'


export default {
  name: 'app',
  components: {
    MainBody,
    Header
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
  /* margin-top: 60px; */
}
h1, h2, h3, div, p, span, input {
  /* font-family: 'Roboto'; */
}
</style>
