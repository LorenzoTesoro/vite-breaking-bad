<script>
import CharactersList from "./CharactersList.vue";
import ResultsCounter from "./ResultsCounter.vue";

export default {
  name: "AppMain",
  components: {
    CharactersList,
    ResultsCounter,
  },
};
</script>

<template>
  <main>
    <ResultsCounter />
    <CharactersList />
  </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;

main {
  background-color: $light;
  max-width: 1200px;
  margin: 0 auto;
  padding: 3rem;

  .found_results {
    background-color: $clr-primary;
    color: $light;
    padding: 1rem;
    margin-bottom: 1rem;
  }
  .card {
    background-color: $clr-primary;
  }
}
</style>
