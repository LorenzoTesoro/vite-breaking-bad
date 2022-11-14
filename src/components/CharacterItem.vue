<script>
export default {
  name: "CharacterItem",
  props: {
    character: Object,
  },
};
</script>

<template>
  <div class="col gy-5">
    <div class="card">
      <div>
        <img
          class="card-img-top p-3"
          :src="character.img"
          :alt="character.name"
        />
      </div>
      <div class="card-body text-center">
        <h4 class="card-title pb-2">{{ character.name }}</h4>
        <h5 class="card-text">{{ character.category }}</h5>
        <p class="card-text">{{ character.status }}</p>
      </div>
    </div>
    <!-- /. card layout -->
  </div>
  <!-- /. col -->
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

.card {
  background-color: $clr-primary;
  color: $light;
  height: 100%;

  .card-text {
    color: $light-dark;
  }
}
</style>
