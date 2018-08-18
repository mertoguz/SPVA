<template>
  <div class="movie-details">
    <div class="movie-not-found" v-if="movie.Error">
      <h2 v-text="movie.Error"></h2>
    </div>
    <div v-else>
      <h1>{{ movie.Title }}</h1>
    <img :src="movie.Poster" />
    <div v-if="movie" class="informations">
      <div class="information">
          <h4>Year:</h4><span> {{ movie.Year }}</span>
      </div>
      <div class="information">
          <h4>IMDB:</h4><span> {{ movie.imdbRating }}</span>
      </div>
      <div class="information">
          <h4>Genre:</h4><span> {{ movie.Genre }}</span>
      </div>
      <div class="information">
          <h4>Director:</h4><span> {{ movie.Director }}</span>
      </div>
      <div class="information">
          <h4>Actors:</h4><span> {{ movie.Actors }}</span>
      </div>
      <div class="information">
          <h4>Plot:</h4><span> {{ movie.Plot }}</span>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  props: { 
    'movie' : {}
    },
}
</script>

<style scoped>
.movie-details {
  margin-top: 50px;
}

.movie-not-found {
  margin-top: 100px;
  text-align: center;
}

h1 {
  text-align: center;
  border-bottom: 1px solid gray;
  width: 50%;
  margin: 0 auto;
  padding-bottom: 10px;
}

h4 {
  display: inline;
}

.informations {
  display: inline-block;
  position: absolute;
  padding-left: 40px;
}

.information {
  margin-top: 25px;
}
</style>
