<template>
  <div class="card text-center m-3">
    <h5 class="card-header">Simple GET Request</h5>
    <div class="card-body">Random cocktail: {{ data }}</div>
  </div>
</template>

<script>
const axios = require("axios");
export default {
  name: "App",
  data() {
    return {
      data: {}
    };
  },
  beforeMount() {
    this.getName();
  },
  methods: {
    async getName() {
      const { data } = await axios.get(
        "https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=Bourbon"
      );
      this.data = data;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
