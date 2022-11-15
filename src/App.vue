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
  },
  mounted() {
    this.callApi(this.store.API_URL);
    this.visible = true;
    console.log(this.store);
    console.log(this.visible);
  },
};
</script>

<template>
  <AppHeader />
  <!-- ./header -->
  <select name="" id="" class="rounded">
    <option value="">Select category</option>
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
