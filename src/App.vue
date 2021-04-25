<template>
  <div class="container">
    <div class="title">
      <img class="bone-img bone" src="../img/骨のフリーアイコン.png" alt="骨" />
      <h1 class="bone">Pet Items</h1>
    </div>
    <Side class="side" />
    <Items class="items" />
  </div>
</template>

<script>
import Side from "./components/side.vue";
import Items from "./components/items.vue";
export default {
  name: "App",
  components: {
    Side,
    Items,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.container {
  display: grid;
  grid-template-columns: 220px 1fr;
  grid-template-rows: 50px 1fr 50px;
}
.title {
  margin: 0;
  font-size: 10px;
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: auto;
  background-color: aqua;
}
.bone-img {
  padding: 0 5px;
  width: 13px;
  height: 13px;
}
.bone {
  display: inline-block;
}
</style>
