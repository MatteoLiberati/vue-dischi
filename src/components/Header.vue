<template>
  <header>
    <img src="../assets/img/logo.png" alt="logo" />
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
    width: 45px;
    padding: 8px;
  }
}
</style>
