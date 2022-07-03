<template>
  <lottory :items="items"></lottory>
</template>

<script lang="ts">
import { defineComponent, ref, onBeforeMount, onMounted } from 'vue';
import lottory from './components/lottory.vue'

// ref reactive 都是将数据变成响应式数据

export default defineComponent({
  name: 'App',
  components: {
    lottory
  },
  // setup 相当于 beforeCreate 和 created 在组件创建之前
  setup() {
    const items = [
      {id:1, position: {}},
      {id:2, position: {left:'60px',top:'0'}},
      {id:3, position: {left:'120px', top:'0'}},
      {id:4, position: {left:'120px',top:'60px'}},
      {id:5, position: {left:'120px',top:'120px'}},
      {id:6, position: {left:'60px',top:'120px'}},
      {id:7, position: {left:'0',top:'120px'}},
      {id:8, position: {left:'0',top:'60px'}},  
    ]

    return {items}
  }
});
</script>

<style>

</style>
