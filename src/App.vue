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
import axios from "axios";

export default {
  name: "App",
  components: {
    axios,
    Header,
    Main,
  },
};
</script>

<style lang="scss">
// STYLE IMPORT
@import "@/styles/mixins.scss";
@import "~@fontsource/roboto/index.css";
@import "~@fontsource/roboto/700.css";
// GENERAL
body {
  font-family: roboto, sans-serif;
  #app {
    height: 100vh;
    @include flex(column);
  }
}
</style>
