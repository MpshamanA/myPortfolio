<template>
  <main id="main">
    <div id="items" v-for="item in items" :key="item.id">
      <img :src="item.path" alt="画像" />
      <p>¥:{{ item.value }}</p>
      <p>種類:{{ item.type }}</p>
      <button><a :href="item.link">購入先</a></button>
    </div>
  </main>
</template>

<script>
import items from "../assets/items.json";
export default {
  name: "side",
  data() {
    return {
      items: items,
    };
  },
};
</script>

<style scoped>
#main {
  grid-column-start: 2;
  grid-column-start: auto;
  grid-row-start: 2;
  grid-row-end: auto;
  background-color: teal;
}
#items {
  display: inline-block;
  padding-left: 20px;
}
</style>
