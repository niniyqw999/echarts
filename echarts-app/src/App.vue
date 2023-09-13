<script setup>
import { provide } from 'vue';
import * as echarts from 'echarts'
import axios from 'axios'

//设置基准路径
axios.defaults.baseURL='http://localhost:8888'

provide('echarts',echarts)
provide('axios',axios)
</script>

<template>
<router-view></router-view>
</template>

<style>
body{
  background: url(./assets/bg.jpg)top center no-repeat; 
}
</style>
