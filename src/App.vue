<template>
  <div id="app">
  <PageTitle/>
  <MovieChoice/>
  </div>
</template>

<script>
import MovieChoice from './components/MovieChoice.vue'
import PageTitle from './components/PageTitle.vue'


export default {
  name: 'app',
  components: {
    MovieChoice,
	PageTitle
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
