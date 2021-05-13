<template>
  <div>
    <aside class="side sticky">
      <h2>TYPE</h2>
      <ul>
        <li class="type">アイテム</li>
        <li class="type">フード</li>
        <li class="type">ペット服</li>
      </ul>
    </aside>
  </div>
</template>

<script>
export default {
  name: "side",
  props: {
    //親コンポーネントでタイプネームを決める

    testtype: String,
  },
  data() {
    return {
      sortKey: "",
    };
  },
};
</script>

<style scoped>
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
