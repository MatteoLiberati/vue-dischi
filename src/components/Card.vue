<template>
  <div class="card">
    <div class="image"></div>
    <h2>Titolo</h2>
    <div class="content">
      <span>Artista</span>
      <span>Anno</span>
      <span>Genere</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
};
</script>

<style scoped lang="scss">
@import "@/styles/vars.scss";
@import "@/styles/mixins.scss";
.card {
  @include flex("column-horizzontal");
  text-align: center;
  width: calc(100% / 8 -40px);
  height: 360px;
  margin: 20px;
  padding: 20px;
  background-color: $primary-color;
  .image {
    width: 144px;
    height: 144px;
    background-color: yellow;
  }
  h2 {
    color: $title-color;
    font-weight: 400;
  }
  .content {
    span {
      display: block;
      color: $char-color;
      margin-bottom: 10px;
      &:first-child {
        font-size: 1.2rem;
      }
      &:last-child {
        color: $title-color;
      }
    }
  }
}
</style>
