<template>
  <div id="app">
    <!-- HEADER -->
    <Header />
    <!-- MAIN -->
    <Main />
  </div>
</template>

<script>
// IMPORT
import Header from "@/components/Header";
import Main from "@/components/Main";
export default {
  name: "App",
  components: {
    Header,
    Main,
  },
};
</script>

<style lang="scss">
// STYLE IMPORT
@import "~@fontsource/roboto/index.css";
@import "~@fontsource/roboto/700.css";
// GENERAL
body {
  @import "@/styles/mixins.scss";
  font-family: roboto, sans-serif;
  #app {
    height: 100vh;
    @include flex(column);
  }
}
</style>
