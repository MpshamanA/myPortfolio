<template>
  <main id="main">
    <div id="items" v-for="item in select" :key="item.id">
      <img :src="item.path" alt="画像" />
      <p>¥:{{ item.value }}</p>
      <!-- <p>種類:{{ item.type }}</p> -->
      <button
        class="btn"
        onclick="return confirm('外部のページへ移動します。よろしいですか？');"
      >
        <a :href="item.link" target="_blank" rel="noopener noreferrer"
          >購入先</a
        >
      </button>
    </div>
  </main>
  <!-- <img src="../assets/img/アイテム1.jpeg" alt="" />
  <img src="../assets/img/アイテム2.jpeg" alt="" />

  <img src="../assets/img/アイテム3.jpeg" alt="" />
  <img src="../assets/img/アイテム4.jpeg" alt="" />
  <img src="../assets/img/アイテム5.jpeg" alt="" />
  <img src="../assets/img/アイテム6.jpeg" alt="" />
  <img src="../assets/img/アイテム7.jpeg" alt="" />
  <img src="../assets/img/アイテム8.jpeg" alt="" />
  <img src="../assets/img/アイテム9.jpeg" alt="" />
  <img src="../assets/img/フード1.jpeg" alt="" />
  <img src="../assets/img/フード2.jpeg" alt="" />
  <img src="../assets/img/フード3.jpeg" alt="" />
  <img src="../assets/img/フード4.jpeg" alt="" />
  <img src="../assets/img/服1.jpeg" alt="" />
  <img src="../assets/img/服2.jpeg" alt="" />
  <img src="../assets/img/服3.jpeg" alt="" />
  <img src="../assets/img/服4.jpeg" alt="" />
  <img src="../assets/img/服5.jpeg" alt="" />
  <img src="../assets/img/服6.jpeg" alt="" />
  <img src="../assets/img/服7.jpeg" alt="" />
  <img src="../assets/img/服8.jpeg" alt="" />
  <img src="../assets/img/服9.jpeg" alt="" /> -->
</template>

<script>
import items from "../assets/items.json";
export default {
  name: "side",
  props: {
    type: String,
  },
  data() {
    return {
      items: items,
      selectItems: items,
    };
  },
  computed: {
    //親コンポーネントでタイプを指定して表示内容を変更する
    select() {
      if (this.type == "") {
        return items;
      } else {
        let tests = this.selectItems;
        let testlist = tests.filter((x) => x.type == this.type); //ここのtypeはpropsで指定している
        return testlist;
      }
    },
  },
};
</script>

<style scoped>
#main {
  grid-column-start: 2;
  grid-column-start: auto;
  grid-row-start: 2;
  grid-row-end: auto;
  background-color: #f8f8f8;
}
#items {
  display: inline-block;
  padding-top: 20px;
  padding-left: 20px;
  padding: 20px 0 20px 20px;
}
#items p {
  text-align: right;
}
#items img {
  width: 250px;
  height: 250px;
}
</style>
