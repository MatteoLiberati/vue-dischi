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
@import "@/styles/general.scss";
</style>
