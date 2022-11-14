<script>
import axios from "axios";
import { store } from "./store.js";

export default {
  name: "App",
  data() {
    return {
      store,
    };
  },
  methods: {
    callApi(url) {
      axios
        .get(url)
        .then((response) => {
          console.log(response);
          this.store.characters = response.data.results;
        })
        .catch((err) => {
          console.error(err.message);
          this.store.error = err.message;
        });
    },
  },
  mounted() {
    this.callApi(this.store.API_URL);
    console.log(this.store);
  },
};
</script>

<template>
  <header>
    <h1>Breaking Bad Api</h1>
    <select name="" id="">
      <option value="">Select Category</option>
    </select>
  </header>
  <!-- ./header -->

  <main>
    <div class="container">
      <div class="found_results">Found x characters</div>
      <div class="card"></div>
    </div>
  </main>
  <!-- ./main -->
</template>

<style lang="scss">
.container {
  background-color: white;
  max-width: 1140px;
  margin: 0 auto;
}
</style>
