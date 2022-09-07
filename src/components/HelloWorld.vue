<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>{{ info.joke }}</h3>
    <button class="my-btn">Une autre citation !</button>
  </div>
</template>

<script>
const axios = require('axios');

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      info: null,
    }
  },
  mounted() {
    axios
      .get('https://chuckn.neant.be/api/rand')
      .then(response => (this.info = response))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
button.my-btn {
  background-color: #607196;
  color: #fff;
  border: none;
  padding: 1rem 3rem;
}
button.my-btn:hover {
  background-color: #425376;
  color: #fff;
  border: none;
  padding: 1rem 3rem;
  cursor: pointer;
}
</style>
