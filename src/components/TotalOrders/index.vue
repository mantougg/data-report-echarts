<template>
  <common-card
  title="累计订单量"
  value="2,157,420"
  >
  <template>
   <div id="total-orders-chart" :style="{ width: '100%', height: '100%' }"></div>
  </template>
  <template v-slot:footer>
    <span>昨日订单量</span>
    <span class="emphasis">2,000,000</span>
  </template></common-card>
</template>

<script>
import commonCardMixin from '../../mixins/commonCardMixin'

export default {
  mixins: [commonCardMixin],
  mounted () {
    const chartDom = document.getElementById('total-orders-chart')
    console.log(this)
    const chart = this.$echarts.init(chartDom)
    chart.setOption({
      xAxis: {},
      yAxis: {},
      series: [{
        type: 'line',
        data: [620, 432, 220, 534, 790, 432, 320, 532, 320, 220, 620]
      }]
    })
  }
}
</script>
