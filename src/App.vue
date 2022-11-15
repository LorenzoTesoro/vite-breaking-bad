<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import { store } from "./store.js";

export default {
  name: "App",
  data() {
    return {
      store,
      loading: false,
    };
  },
  components: {
    AppHeader,
    AppMain,
  },
  methods: {
    callApi(url) {
      this.loading = true;
      axios
        .get(url)
        .then((response) => {
          console.log(response);
          this.store.characters = response.data;
          console.log(this.store.characters);
        })
        .catch((err) => {
          console.error(err.message);
          this.store.error = err.message;
        })
        .finally(() => {
          this.loading = false;
        });
    },
    switchOption(event) {
      //console.log(event.target.value);

      if (event.target.value == 1) {
        const url = `${this.store.API_URL}?category=Breaking+Bad`;
        this.callApi(url);
      } else if (event.target.value == 2) {
        const url = `${this.store.API_URL}?category=Better+Call+Saul`;
        this.callApi(url);
      }
    },
  },
  mounted() {
    this.callApi(this.store.API_URL);
    this.visible = true;
  },
};
</script>

<template>
  <AppHeader />
  <!-- ./header -->
  <select name="" id="" class="rounded" @change="switchOption">
    <option>Select category</option>
    <option value="1">Breaking Bad</option>
    <option value="2">Better Call Saul</option>
  </select>
  <div class="loader" v-if="loading">
    <h2 class="text-light text-center">Loading...</h2>
  </div>
  <AppMain v-else />
  <!-- ./main -->
</template>

<style lang="scss" scoped>
select {
  padding: 0.25rem;
  position: relative;
  left: 250px;
  margin-bottom: 1rem;
}
</style>
