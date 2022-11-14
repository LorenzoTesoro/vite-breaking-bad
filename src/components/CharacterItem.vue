<script>
export default {
  name: "CharacterItem",
  props: {
    character: Object,
  },
};
</script>

<template>
  <div class="col">
    <div class="card">
      <div>
        <img class="card-img-top" :src="character.img" :alt="character.name" />
      </div>
      <div class="card-body">
        <h4 class="card-title">{{ character.name }}</h4>
        <h5 class="card-text">{{ character.category }}</h5>
        <p class="card-text">{{ character.status }}</p>
      </div>
    </div>
    <!-- /. card layout -->
  </div>
  <!-- /. col -->
</template>
