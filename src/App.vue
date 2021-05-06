<template>
  <div id="app">
    <!-- HEADER -->
    <Header>
      <a href="#"><img src="@/assets/img/logo.png" alt="logo"/></a>
    </Header>
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
