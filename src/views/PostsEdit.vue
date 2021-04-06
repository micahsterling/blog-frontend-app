<template>
  <div class="Posts-edit">
    <h1>{{ message }}</h1>
    <form v-on:submit.prevent="submit()">
      <h1>Edit a Post</h1>
      <ul>
        <li class="text-danger" v-for="error in errors" v-bind:ket="error">
          {{error}}
          </li>
        </ul>
        <div class="form-group">
        <label>Title:</label>
        <input type="text" class="form-control" v-model="posts.title">
      </div>
      </form>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function () {
    return {
      message: "Welcome to test.js!",
    };
  },
  created: function () {},
  methods: {},
};
</script>