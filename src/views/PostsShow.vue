<template>
  <div class="show">
    <h1>{{ message }}</h1>
    <p>title: {{posts.title}} </p>
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
    };
  },
  created: function () {
    console.log(this.$route.params.id);
    axios.get("/api/posts/" + this.$route.params.id).then((response) => {
      console.log(response.data);
      this.posts = response.data;
    });
  },
  methods: {},
};
</script>