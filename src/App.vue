<template>
  <div id="app" class="container">
    <h1>MOVIE DETAILS FINDER</h1>
    <search v-on:searchMovie="searchMovie"/>
    <movie-details :movie=movie />
  </div>
</template>

<script>
import search from './components/search'
import movieDetails from './components/movie-details'

export default {
  name: 'app',
  components: { search, movieDetails },
  data () {
    return {
      movie: null
    }
  },
  methods: {
    searchMovie: function (query) {
      fetch(`https://www.omdbapi.com/?t=${query}&apikey=c5d05685`)
      .then((response) => { return response.json() })
      .then((response) => { this.$set(this, 'movie', response);})
    }
  },
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  text-transform: uppercase;
  text-align: center;
}

footer {
  position: absolute;
  bottom: 25px;
  margin: 0 auto;
}
</style>
