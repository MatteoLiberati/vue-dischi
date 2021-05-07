<template>
  <section>
    <label for="selector">Filter by gender</label>
    <div>
      <div class="container-select">
        <select
          v-model.trim="value"
          @change="$emit('selection', value)"
          name="selector"
          id="selector"
        >
          <option class="option" value="All">All</option>
          <option
            v-for="(element, index) in list"
            :key="element + index"
            :value="element"
            >{{ element }}</option
          >
        </select>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Search",
  props: ["list"],
  data() {
    return {
      value: "All",
    };
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/vars.scss";
@import "@/styles/mixins.scss";
section {
  margin-bottom: 10px;
  @include flex("center");
  label {
    color: $title-color;
    text-transform: uppercase;
    margin-right: 10px;
  }
  & > div {
    position: relative;
    .container-select {
      select {
        min-width: 150px;
        height: 25px;
        appearance: none;
        outline: none;
        border-radius: 10px;
        background-color: $title-color;
        color: $background-color;
        text-align: center;
        cursor: pointer;
        border: 1px outset $char-color;
      }
      &:before {
        position: absolute;
        top: 42%;
        right: 5%;
        content: "";
        border: 8px solid transparent;
        border-top: 8px solid $background-color;
      }
    }
  }
}
</style>
