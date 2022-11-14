<script>
import CharactersList from "./CharactersList.vue";

export default {
  name: "AppMain",
  components: {
    CharactersList,
  },
};
</script>

<template>
  <div class="main">
    <div class="found_results">Found x characters</div>
    <CharactersList />
  </div>
</template>

<style lang="scss" scoped>
.main {
  background-color: white;
  margin: 0 auto;
  padding: 1rem 1.5rem;
  .found_results {
    background-color: #2e3a46;
    color: white;
  }
}
</style>
