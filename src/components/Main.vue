<template>
  <main>
    <div class="cards">
      <Card
        v-for="(element, index) in album"
        :key="element + index"
        :content="element"
      />
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
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.album = res.data.response;
        console.log(this.album);
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
}
</style>
