<script>
import axios from "axios";
import { store } from "./store.js";
import SiteHeader from "./components/SiteHeader.vue";

export default {
  name: "App",
  data() {
    return {
      store,
    };
  },
  components: {
    SiteHeader,
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
  <SiteHeader />
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
