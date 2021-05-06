<template>
  <header>
    <a href="#"><img src="../assets/img/logo.png" alt="logo"/></a>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped lang="scss">
@import "@/styles/vars.scss";
// HEADER STYLE
header {
  background-color: $primary-color;
  img {
    width: 60px;
    padding: 8px;
  }
}
</style>
