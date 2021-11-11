<template>
  <div id="app">
    <Container />
    <Footer />
  </div>
</template>

<script>
import Container from './components/Container.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Container,
    Footer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
