<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div v-if="result != null">
      <h3 class="my-citation" v-bind="result" :key="result.id">{{ result }}</h3>
      <button class="my-btn" @click="getChuckFact">Une autre citation !</button>
    </div>
    <div v-else>
      <button class="my-btn" @click="getChuckFact">Une citation !</button>
    </div>
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
      result: null,
    }
  },
  methods: {
    getChuckFact() {
      axios
      .get('https://api.chucknorris.io/jokes/random')
      .then(response => (this.result = response.data.value))
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3.my-citation {
  margin: 40px 0 0;
  margin-bottom: 5rem;
  text-align: center;

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
