<template>
  <main>
    <div v-if="loader" class="cards">
      <Card
        v-for="(element, index) in album"
        :key="element + index"
        :content="element"
      />
    </div>
    <div v-else class="loading">
      <img src="@/assets/img/logo.png" alt="logo" />
      LOADING...
    </div>
  </main>
</template>

<script>
import Card from "@/components/Card";
import axios from "axios";
export default {
  name: "Main",
  components: {
    Card,
    axios,
  },
  data() {
    return {
      album: [],
      loader: false,
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.album = res.data.response;
        this.loader = true;
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/vars.scss";
@import "@/styles/mixins.scss";
// MAIN
main {
  flex-grow: 1;
  background-color: $background-color;
  padding-top: 80px;
  overflow: auto;
  .cards {
    @include flex("horizontal");
    flex-wrap: wrap;
  }
  .loading {
    height: 100%;
    width: 100%;
    @include flex("column-center");
    color: $title-color;
    font-size: calc(1.8vw + 1.8%);
    img {
      width: 300px;
      animation: pulse 1s alternate infinite;
    }
  }
}
@keyframes pulse{
  to {
    transform: scale(1);
  }
  from {
    transform: scale(1.1);
  }
}
</style>
