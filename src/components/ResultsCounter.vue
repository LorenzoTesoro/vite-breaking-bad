<script>
import { store } from "../store.js";

export default {
  name: "ResultsCounter",
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="found_results">
    Found {{ store.characters.length }} characters
  </div>
</template>
