<template>
  <div>
    <header><h1>Echarts大数据可视化</h1></header>
    <section class="container">
      <section class="itemLeft">
        <itemPage>
          <itemOne></itemOne>
        </itemPage>
        <itemPage>
          <itemTwo></itemTwo>
        </itemPage>
      </section>
      <section class="itemCenter">
        <mapPage></mapPage>
      </section>
      <section class="itemRight">
        <itemPage>
          <itemThree></itemThree>
        </itemPage>
        <itemPage>
          <itemFour></itemFour>
        </itemPage>
      </section>
    </section>
  </div>
</template>

<script setup>
import itemOne from '../components/itemOne.vue';
import itemPage from '../components/itemPage.vue';
import itemThree from '../components/itemThree.vue';
import itemTwo from '../components/itemTwo.vue';
import itemFour from '../components/itemFour.vue';
import mapPage from '../components/mapPage.vue';
import { inject } from 'vue';

let $echarts=inject('echarts')
let $http=inject('axios')
console.log($echarts)
console.log($http)
</script>

<style lang="less" scoped>
header {
  height: 1rem;
  width: 100%;
  background-color: rgba(0, 0, 255, 0.2);
  // 标题的文字样式
  h1 {
    font-size: 0.375rem;
    color: #fff;
    text-align: center;
    line-height: 1rem;
  }
}

// 大容器的样式
.container {
  // 最大最小的宽度
  min-width: 1200px;
  max-width: 2048px;
  margin: 0 auto;
  padding: 0.125rem 0.125rem 0;
  // background-color: gray;
  display: flex;
  // 设置左右在页面的份数
  .itemLeft,
  .itemRight {
    flex: 3;
  }
  .itemCenter {
    flex: 5;
    height: 10.5rpx;
    border: 1px solid blue;
    padding:  0.125rem;
    margin: .25rem;
  }
}
</style>