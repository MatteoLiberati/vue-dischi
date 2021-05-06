<template>
  <div class="card">
    <div class="image">
      <a href="#"><img :src="content.poster" :alt="content.title"/></a>
    </div>
    <div class="content">
      <h3>{{ content.title }}</h3>
      <span>{{ content.author }}</span>
      <span>{{ content.year }}</span>
      <span>{{ content.genre }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["content"],
};
</script>

<style scoped lang="scss">
@import "@/styles/vars.scss";
@import "@/styles/mixins.scss";
.card {
  @include flex("column-horizzontal");
  text-align: center;
  width: calc(100% / 8 -40px);
  height: 370px;
  margin: 20px;
  padding: 20px;
  background-color: $primary-color;
  .image {
    img {
      width: 144px;
      height: 144px;
      object-fit: cover;
    }
  }
  .content {
    max-width: 144px;
    h3 {
      font-size: 1.3rem;
      text-transform: uppercase;
      color: $title-color;
      font-weight: 400;
      margin: 20px 0;
    }
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
