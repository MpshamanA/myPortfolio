<template>
  <div>
    <aside class="side">
      <h2>TYPE</h2>
      <ul>
        <li class="type">リード</li>
        <li class="type">ペット服</li>
        <li class="type">おもちゃ</li>
        <li class="type">おやつ</li>
      </ul>
    </aside>
  </div>
</template>

<script>
export default {
  name: "side",
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
  background-color: blueviolet;
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
