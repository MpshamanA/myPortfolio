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
        <!-- サイドバーのアイテムを選択すると背景色がグレーになる
        カーソルを載せると背景色がライトグレーになる -->
        <li
          @click="select('アイテム'), switchColor1()"
          class="type"
          :class="{
            gray: sideItem,
            white: !sideItem,
            lightGray: hoverItem && !sideItem,
          }"
          @mouseover="mouseover1()"
          @mouseleave="mouseleave1()"
        >
          アイテム
        </li>
        <!-- サイドバーのフードを選択すると背景色がグレーになる
        カーソルを載せると背景色がライトグレーになる -->
        <li
          @click="select('フード'), switchColor2()"
          class="type"
          :class="{
            gray: sideFood,
            white: !sideFood,
            lightGray: hoverFood && !sideFood,
          }"
          @mouseover="mouseover2()"
          @mouseleave="mouseleave2()"
        >
          フード
        </li>
        <!-- サイドバーのペット服を選択すると背景色がグレーになる
        カーソルを載せると背景色がライトグレーになる -->
        <li
          @click="select('ペット服'), switchColor3()"
          class="type"
          :class="{
            gray: sideFastion,
            white: !sideFastion,
            lightGray: hoverFastion && !sideFastion,
          }"
          @mouseover="mouseover3()"
          @mouseleave="mouseleave3()"
        >
          ペット服
        </li>
      </ul>
    </aside>
    <Items
      :class="{ fedeIn: classSwitch, fedeIn2: !classSwitch }"
      :type="type"
    />
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
      sideItem: false,
      sideFood: false,
      sideFastion: false,
      hoverItem: false,
      hoverFood: false,
      hoverFastion: false,
      classSwitch: false,
    };
  },
  methods: {
    select(e) {
      this.type = e;
    },
    switchColor1() {
      //アイテム
      this.sideItem = true;
      this.sideFood = false;
      this.sideFastion = false;
      this.classSwitch = !this.classSwitch;
    },
    switchColor2() {
      //フード
      this.sideItem = false;
      this.sideFood = true;
      this.sideFastion = false;
      this.classSwitch = !this.classSwitch;
    },
    switchColor3() {
      //ペット服
      this.sideItem = false;
      this.sideFood = false;
      this.sideFastion = true;
      this.classSwitch = !this.classSwitch;
    },
    mouseover1() {
      //アイテム
      this.hoverItem = true;
      this.hoverFood = false;
      this.hoverFastion = false;
    },
    mouseover2() {
      //フード
      this.hoverItem = false;
      this.hoverFood = true;
      this.hoverFastion = false;
    },
    mouseover3() {
      //ペット服
      this.hoverItem = false;
      this.hoverFood = false;
      this.hoverFastion = true;
    },
    mouseleave1() {
      //アイテム
      this.hoverItem = false;
    },
    mouseleave2() {
      //フード
      this.hoverFood = false;
    },
    mouseleave3() {
      //ペット服
      this.hoverFastion = false;
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
  grid-template-columns: 180px 1fr;
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
  cursor: pointer;
}
ul {
  margin: 0;
  padding: 0;
}
.gray {
  background-color: #cccccc;
  transition-duration: 0.2s;
}
.white {
  background-color: white;
}
.lightGray {
  background-color: #eeeeee;
}
.fedeIn {
  animation: 0.5s fadeIn;
}
.fedeIn2 {
  animation: 0.5s fadeIn2;
}
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes fadeIn2 {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
