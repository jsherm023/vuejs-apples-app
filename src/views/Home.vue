<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p v-for="apple in apples"> {{apple.variety}}</p>
  </div>
</template>

<style>
</style>

<script>
  var axios = require('axios');
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      apples: []
    };
  },
  created: function() {
    axios.get('http://localhost:3000/api/apples').then(function(response){
      console.log(response.data);
      this.apples = response.data;
    }.bind(this))
  },
  methods: {},
  computed: {}
};
</script>
