<template>
<div class="search">
    <h1>WELCOME TO MOVIE DETAILS FINDER</h1>
    <div class="search-box">
      <input type="text" placeholder="Search a movie by name" v-model="query" @keypress.enter="searchMovie"/>
      <button @click="searchMovie">Search</button>
    </div>
</div>
</template>

<script>
export default {
  data () {
    return {
      query: ''
    }
  },
  methods: {
    searchMovie () {
      this.$emit('searchMovie', this.query);
      this.query = '';
    }
  }
}
</script>

<style scoped>
  .search {
    text-align: center;
  }
  .search-box {
    margin-top: 50px;
  }
  input {
    padding: 5px 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
    height: 20px;
  }

  button {
    border: 1px solid #ccc;
    border-radius: 5px;
    height: 30px;
    background-color: chocolate;
    color: #fff;
  }  
</style>


