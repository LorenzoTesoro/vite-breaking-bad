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
  <AppMain />
  <!-- ./main -->
</template>

<style lang="scss">
.container {
  background-color: white;
  max-width: 1140px;
  margin: 0 auto;
}
</style>
