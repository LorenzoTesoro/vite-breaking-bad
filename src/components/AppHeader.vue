<script>
export default {
  name: "AppHeader",
};
</script>

<template>
  <header>
    <div class="logo">
      <img
        src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/77/Breaking_Bad_logo.svg/369px-Breaking_Bad_logo.svg.png"
        alt=""
      />
    </div>
    <h1 class="ps-3">Breaking Bad Api</h1>
  </header>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;

header {
  display: flex;
  align-items: center;
  padding: 2rem 0 2rem 1rem;
  .logo {
    width: 50px;
  }
  h1 {
    color: $light;
  }
}
</style>
