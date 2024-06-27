<script setup>
import { reactive } from 'vue'
import Counter from './Counter.vue';

const data = reactive({
  msg: "This is an about page bbb",
  msg2: "<h1>hello </h1>",
  borderColor: "redborder",
  age: 17,
  age18class: "grt18",
  agelessclass: "lest18",
  flexWidth: "100px",
  flexHeight: "100px",
  flexColor: "green",
  backGroundColorChanged: "bgcolor1",
});

function changeBackGroundColor() {
  console.log(data.backGroundColorChanged);
  if (data.backGroundColorChanged === "bgcolor1") {
    data.backGroundColorChanged = "bgcolor2";
  } else {
    data.backGroundColorChanged = "bgcolor1";
  }
}
</script>

<template>
  <div v-html="data.msg2"></div>
  <div v-text="data.msg2"></div>
  <div :class="data.borderColor"></div>
  <div :class="data.age >= 18 ? data.age18class : data.agelessclass">{{ data.age }}</div>
  <div :style="{ width: data.flexWidth, height: data.flexHeight, backgroundColor: data.flexColor }">
    <div>width:<input v-model="data.flexWidth"></div>
    <div>height:<input v-model="data.flexHeight"></div>
    <div>color:<input v-model="data.flexColor"></div>
  </div>
  <div>
    <button @click="changeBackGroundColor()">修改背景颜色</button>
  </div>
  <div :class="data.backGroundColorChanged">
  </div>
  <Counter></Counter>
</template>

<style scoped>
.blackborder{
  width: 100px;
  height: 100px;
  border: 1px solid black;
}
.redborder{
  width: 100px;
  height: 100px;
  border: 1px solid red;
}
.grt18{
  width: 100px;
  height: 100px;
  background-color: greenyellow;
}
.lest18{
  width: 100px;
  height: 100px;
  background-color: red;
}
.bgcolor1{
  width: 100px;
  height: 100px;
  background-color: greenyellow;
}
.bgcolor2{
  width: 100px;
  height: 100px;
  background-color: #d3b17d;
}

</style>