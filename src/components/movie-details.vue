<template>
  <div class="movie-details" v-if="movie">
    <div class="movie-not-found col-xs-12" v-if="movie.Error">
      <h2 v-text="movie.Error"></h2>
    </div>
    <div v-else>
      <h1>{{ movie.Title }}</h1>
      <div v-if="movie" class="content row">
        <div class="movie-poster col-md-6 col-lg-4">
          <img :src="movie.Poster" />
        </div>
        <div class="informations col-md-6 col lg-8">
          <div class="information">
              <h5>Year:</h5><span> {{ movie.Year }}</span>
          </div>
          <div class="information">
              <h5>IMDB:</h5><span> {{ movie.imdbRating }}</span>
          </div>
          <div class="information">
              <h5>Genre:</h5><span> {{ movie.Genre }}</span>
          </div>
          <div class="information">
              <h5>Director:</h5><span> {{ movie.Director }}</span>
          </div>
          <div class="information">
              <h5>Actors:</h5><span> {{ movie.Actors }}</span>
          </div>
          <div class="information">
              <h5>Plot:</h5><span> {{ movie.Plot }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: { 
    'movie' : null
    },
}
</script>

<style scoped>
.movie-details {
  margin: 50px 0;
}

.movie-not-found {
  margin-top: 100px;
  text-align: center;
}

.movie-poster {
  text-align: center;
}

h1 {
  text-align: center;
  border-bottom: 1px solid gray;
  padding-bottom: 10px;
}

h5 {
  display: inline;
}

.content {
  margin-top: 30px;
}

.informations {
  
}

.information {
  margin-top: 25px;
}

@media screen and (max-width: 768px) {
    .informations {
      text-align: center;
    }
  }
</style>
