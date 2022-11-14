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
    };
  },
  components: {
    AppHeader,
    AppMain,
  },
  methods: {
    callApi(url) {
      axios
        .get(url)
        .then((response) => {
          console.log(response);
          this.store.characters = response.data;
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
  <AppHeader />
  <!-- ./header -->
  <select name="" id="" class="rounded">
    <option value="">Select category</option>
  </select>
  <AppMain />
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
