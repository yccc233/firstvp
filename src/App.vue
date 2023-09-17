<script setup>
import { ref } from 'vue';

// 定义响应性引用
const msg = ref('这是一条消息');
const rawHtml = ref('<strong>这是一些HTML内容</strong>');
</script>

<template>
  <span>Message: {{ msg }}</span>

  <p>Using text interpolation: {{ rawHtml }}</p>
  
  <p>Using v-html directive: <span v-html="rawHtml"></span></p>
</template>

<style scoped></style>
