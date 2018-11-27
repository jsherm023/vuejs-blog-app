<template>
  <div class="posts">
  <h1>{{ message }}</h1>
    <div class="container">
      <div class="row">
        <div class="col-sm-4" v-for="post in posts">
          <div class="card" style="width: 18rem;">
            <div class="card-body">
              <h5 class="card-title">Title: {{ post.title }}</h5>
              <h6 class="card-subtitle mb-2 text-muted">Body: {{ post.body }}</h6>
              <p class="card-text">Image: {{ post.image }}</p>
              <a href="#" class="card-link">Card link</a>
              <a href="#" class="card-link">Another link</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
</style>

<script>
  var axios = require('axios');
export default {
  data: function() {
    return {
      message: "Take A Look At These Posts!",
      posts: [],
    };
  },
  created: function() {
    axios.get('http://localhost:3000/api/posts').then(function(response){
      console.log(response.data);
      this.posts = response.data;
    }.bind(this))
  },
  methods: {
  },
  computed: {}
};
</script>