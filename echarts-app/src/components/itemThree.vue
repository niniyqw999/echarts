<template>
  <div>
    <h2>库存统计</h2>
    <div class="chart" id="myEcharts"></div>
  </div>
</template>
  
<script setup>
import { inject,onMounted,reactive } from 'vue';

let $echarts=inject('echarts')
let $http=inject('axios')

let data=reactive({})

async function getState(){
  data=await $http({url:'/three/data'})
}

onMounted(() => {
  getState().then(()=>{
    let myChart=$echarts.init(document.getElementById('myEcharts'))
    myChart.setOption({
      legend:{
        top:'bottom'
      },
      tooltip:{
        show:true
      },
      series:[
        {
           type:'pie',
           data:data.data.chartThree.chartData,
           radius:[10,100],
           center:['50%','45%'],
           roseType:'area',
           itemStyle:{
            borderRadius:10
           }
        }
      ]
    })
  })
})
</script>
  
<style lang="less" scoped>
.chart{
  height: 4.5rem;
}
h2 {
  height: 0.6rem;
  color: #fff;
  line-height: 0.6rem;
  font-size: 0.25rem;
  text-align: center;
}
</style>