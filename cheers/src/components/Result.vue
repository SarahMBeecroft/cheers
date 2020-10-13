<template>
  <div class="card text-center m-3">
    <h5 class="card-header">Simple GET Request</h5>
    <div class="card-body">Total vue packages: {{ totalVuePackages }}</div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'get-request',
  data() {
    return {
      totalVuePackages: null,
    };
  },
  created() {
    // Simple GET request using axios
    axios
      .get('https://api.npms.io/v2/search?q=vue')
      .then((response) => (this.totalVuePackages = response.data.total));
    console.log(data);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
