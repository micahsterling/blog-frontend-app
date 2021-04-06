<template>
  <div class="Posts">
    <h1>{{ message }}</h1>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Welcome to Posts!",
    };
  },
  created: function () {},
  methods: {},
};
</script>

