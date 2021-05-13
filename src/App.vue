<template>
  <div class="container">
    <div class="title">
      <img
        class="bone-img bone"
        src="./assets/img/骨のフリーアイコン.png"
        alt="骨"
      />
      <h1 class="bone">Pet Items</h1>
    </div>
    <aside class="side sticky">
      <h2>TYPE</h2>
      <ul>
        <li @click="select('アイテム')" class="type">アイテム</li>
        <li @click="select('フード')" class="type">フード</li>
        <li @click="select('ペット服')" class="type">ペット服</li>
      </ul>
    </aside>
    <!-- <Side class="side" @click="select('アイテム')" /> -->
    <Items class="items" :type="type" />
  </div>
</template>

<script>
import Items from "./components/items.vue";
export default {
  name: "App",
  components: {
    Items,
  },
  data() {
    return {
      type: "",
    };
  },
  methods: {
    select(e) {
      this.type = e;
    },
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
  background-color: #fff;
  top: 0px;
  width: 100%;
  height: 55px;
  position: fixed;
}
.bone-img {
  padding: 0 5px;
  width: 13px;
  height: 13px;
}
.bone {
  display: inline-block;
}
.side {
  box-sizing: border-box;
  padding: 0 10px;
  background-color: #fff;
  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 2;
  grid-row-end: 3;
}
.sticky {
  position: -webkit-sticky;
  position: sticky;
  top: 80px;
}
.type {
  list-style: none;
  padding: 10px;

  margin: 10px 0;
}
ul {
  margin: 0;
  padding: 0;
}
</style>
