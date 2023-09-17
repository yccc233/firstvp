<script setup>
import { ref } from 'vue';

// 定义响应性引用
const msg = ref('我们这周去拉萨了！');
const message = ref('我们这周去拉萨了！');
const rawHtml = ref('我们这周去<span style="font-weight: bold; color: red;">拉萨</span>了！');
let divId = ref("ycc");
let isButtonDisabled = ref(false);


const seen = ref(false);



const eventName = null

const doSomething = function () {
  console.log("你好");
}

const doSomething1 = function () {
  console.log("你好1");
}

const doSomething2 = function (event) {
  event.stopPropagation();
  event.preventDefault();
  console.log("你好2", event);
}

</script>

<template>
  <span>Message: {{ msg }}</span>

  <!-- <p>Using text interpolation: {{ rawHtml }}</p> -->

  <p>Using v-html directive: <span v-html="rawHtml"></span></p>

  <div v-bind:id="divId">
    {{ message.split('').reverse().join('') }}
  </div>

  <button :disabled="isButtonDisabled">Button</button>


  <div :id="`list-${id}`"></div>

  <hr />

  <p v-if="seen">
    Now you see me
  </p>


  <a v-bind:href="`https://www.baidu.com`" target="_blank——ABC"> 百度 </a>




  <a v-on:[eventName]="doSomething" YCC="test"> 点我 </a>

  <div class="test1" @click="doSomething1">
    <button @click="doSomething2">按钮</button>
    <button @contextmenu="doSomething2">按钮</button>
  </div>
</template>

<style scoped>
.test1 {
  width: 100px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
