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
    @import url('https://fonts.googleapis.com/css?family=Raleway');
    body {
        background-color: #35495E;
    }
    #app {
        font-family: 'Raleway', sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 5%;
        background-color: #00D1A0;
        padding: 10px;
        border-radius: 8px;
    }
</style>
