<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div class="container">
      <div class="row">
        <div class="col-sm-4">
          <div class="card" style="width: 18rem;">
            <div class="card-body">
              <h5 class="card-title">Variety: {{ apple.variety }}</h5>
              <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
              <p class="card-text">origin: {{apple.origin }}</p>
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
      message: "Welcome to the show page!",
      apple: {}
    };
  },
  created: function() {
      console.log(this);
      axios.get('http://localhost:3000/api/restaurants/' + this.$route.params.id).then(response => {
        console.log(response.data);
        this.restaurant = response.data;
      });
  },
  methods: {},
  computed: {}
};
</script>