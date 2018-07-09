<template>
  <div>
    <div v-for="(gram, index) in grams">
      <img :src="gram.images.standard_resolution.url" :alt="gram.text" />  
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      access_token: "5345359006.1677ed0.9822de0aa5684d9dbff1ece15d171851",
      url: "https://api.instagram.com/v1/users/self/media/recent/",
      username: "",
      grams: [],
      error: false
    }
  },

  // Fetches posts when the component is created.
  created() {
    axios.get(this.url + "?access_token=" + this.access_token)
      .then(({data}) => {
        console.log(data)
        this.grams = data.data
        this.username = data.data[0].user.username
        this.next_url = data.pagination.next_url
      })
      .catch(function (error) {
        console.log(error)
        this.error = true
      });
  }
}
</script>
