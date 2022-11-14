<script>
import CharacterItem from "./CharacterItem.vue";
import { store } from "../store.js";

export default {
  name: "CharactersList",
  components: {
    CharacterItem,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
    <div class="row row-cols-5">
      <CharacterItem
        :character="character"
        v-for="character in store.characters"
      />
    </div>
  </div>
</template>
