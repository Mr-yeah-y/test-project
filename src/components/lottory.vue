<template>
  <div class="hello">
    <div class="lottory-wrap relative">
      <div v-for="(item,index) in newItems" :key="index" class="lottory-item absolute" :style="item.position">{{item.id}}</div>
      <div class="lottory-btn absolute" @click="onStartLottory(10)">抽奖</div>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent} from 'vue';
let $activeIndex = 0

export default defineComponent({
  name: 'lottory',
  props: {
    items: {
      type: Array,
      default: () => []
    }
  },
  setup(props) {
    const newItems = computed(() => {
      function getNew<T> (item:T) {
        return {...item, isActive:false}
      }
      return props.items.map(getNew)
    })

    const onStartLottory = (steps:number) => {
      let maxTurns = 0
    }

    return {onStartLottory, newItems}
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.relative {
  position: relative;
}
.absolute {
  position: absolute;
}
.lottory-item {
  width: 50px;
  height: 50px;
  background: red;
  line-height: 50px;
  text-align: center;
  color: #fff;
}
.lottory-btn {
  width: 50px;
  height: 50px;
  left: 60px;
  top: 60px;
  background: blue;
  color: #fff;
  font-weight: 600;
  font-size: 20px;
  text-align: center;
  line-height: 50px;
}

</style>
