<template>
  <div class="container">
    <div class="btn-container">
      <button class="movie-btn" type="button" @click="getPic">click me!</button>
    </div>
    <div class="img-container" v-if="image">
      <img :src="image" class="movie-poster"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      // api key
      key: '6edd6f667a316dbecd4fc2732ee85d59',
      baseUrl: '',
      image: ''
    }
  },
  methods: {
    /* The app uses the Movie DB API to access film posters. Images in this API need 3 parameters: base url, image size and poster path. Base url and image size need to be fetched from the Configuration API */
    urlConfig: function() {
      const vm = this;
      axios.get('https://api.themoviedb.org/3/configuration?api_key=' + this.key)
      .then(function(data) {
        // Getting base url and poster size
        vm.baseUrl = data.data.images.base_url + data.data.images.poster_sizes[3];
      })
    },
    getPic: function() {
      const vm = this;
      /* The API returns 500 pages of results with 20 on each page. To get a random image out of all these, random numbers are picked, one between 1-500 for the page number, and then one between 1-19 for the result number */
      let page = Math.floor(Math.random() * 500) + 1;
      let result = Math.floor(Math.random() * 19) + 1;

      /* Here the Discover API is accessed to fetch a list of films with a vote average of at least 7 and excluding adult films (we're professionals, after all) on a page number that was randomized earlier */
      axios.get('https://api.themoviedb.org/3/discover/movie?api_key=' + this.key + "&language=en-US&include_adult=false&vote_average.gte=7&page=" + page)
      .then(function(data) {
        if (data.data.results[result].poster_path != null) {
          /* Setting the full image url from the base url and the poster path of a random result */
          vm.image = vm.baseUrl + data.data.results[result].poster_path;
        } else {
          // If a film doesn't have a poster path in the database, a 404 image is displayed
          vm.image = require("../../assets/lal_edited.jpg");
          console.log("No image found!");
        }
      })
    }
  },
  created() {
    this.urlConfig();
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Balsamiq+Sans&display=swap');

.btn-container {
  padding: 20px 0;
  margin-bottom: 30px;
}

.movie-btn {
  font-family: 'Balsamiq Sans', cursive;
  font-size: 22px;
  letter-spacing: 1px;
  width: 140px;
  height: 50px;
  border: none;
  background-color: rgb(100, 108, 145);
  color: rgb(255, 255, 255);
}

.movie-btn:active {
  background-color: rgb(57, 63, 92);
  color: rgb(182, 182, 182);
}

.movie-btn:focus {
  outline: none;
}

.img-container {
  padding: 40px 30px;
  width: 60vw;
  max-width: 400px;
  margin: auto;
  background-color: #fff;
  box-shadow: 0px 5px 15px rgb(20, 20, 20);
}

img {
  max-width: 100%;
}
</style>
