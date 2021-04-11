<template>
  <div class="Posts">
    <h1>{{ message }}</h1>
    <p>Search Titles: <input type="text" v-model="searchTerm"></p>
    <div v-for="post in filterBy(posts, searchTerm, 'title')">
      <router-link v-bind:to="`/posts/${post.id}`">{{ post.title }}</router-link>
      <hr>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
import Vue2Filters from "vue2-filters";
export default {
  mixins: [Vue2Filters.mixin],
  data: function () {
    return {
      message: "Welcome to Posts!",
      posts: [],
      searchTerm: "",
    };
  },
  created: function () {
    this.postsIndex();
  },
  methods: {
    postsIndex: function () {
      console.log("in post index");
      axios.get("/api/posts").then((response) => {
        console.log(response.data);
        this.posts = response.data;
      });
    },
  },
};
</script>

