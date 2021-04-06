<template>
  <div class="posts-show">
    <h1>{{ message }}</h1>
    <p>id: {{posts.id}} </p>
    <p>title: {{posts.title}} </p>
    <p>body: {{posts.body}} </p>
    <p>image: {{posts.image}} </p>
    <img v-bind:src="posts.image">
    <br />
    <router-link v-bind:to="`/posts/${this.$route.params.id}/edit`">Edit posts</router-link>
    <br />
    <button v-on:click="deletePosts()">Delete Post</button>
  </div>
</template>

<style>
</style>
<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Welcome to the Show",
      posts: {},
    };
  },
  created: function () {
    console.log(this.$route.params.id);
    axios.get("/api/posts/" + this.$route.params.id).then((response) => {
      console.log(response.data);
      this.posts = response.data;
    });
  },
  methods: {
    deletePost: function () {
      console.log("deleting post");
      axios.delete(`/api/posts/${this.$route.params.id}`).then((response) => {
        console.log(response.data);
        this.post = response.data;
      });
    },
  },
};
</script>