<template>
  <main>
    <Search v-if="loader" @selection="select" :list="musicgenre" />
    <div v-if="loader" class="cards">
      <Card
        v-for="(element, index) in albumFilter"
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
import Search from "@/components/Search";
export default {
  name: "Main",
  components: {
    Card,
    Search,
  },
  data() {
    return {
      album: [],
      albumFilter: [],
      loader: false,
      musicgenre: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        res.data.response.forEach((element) => {
          if (!this.musicgenre.includes(element.genre)) {
            this.musicgenre.push(element.genre);
          }
        });
        this.album = res.data.response;
        this.albumFilter = this.album;
        this.loader = true;
      })
      .catch((err) => {
        console.log(err);
      });
  },
  methods: {
    // value = valore dell'option
    select(value) {
      if (value !== "All") {
        console.log("enter");
        this.albumFilter = this.album.filter((item) => {
          return item.genre == value;
        });
      } else {
        console.log("enter");
        this.albumFilter = this.album;
      }
    },
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
@keyframes pulse {
  to {
    transform: scale(1);
  }
  from {
    transform: scale(1.1);
  }
}
</style>
