<template>
  <MonthlyChart 
    v-if="state.isLoaded" 
    v-bind:chartData="state.chartData" 
    v-bind:chartOptions="state.chartOptions" 
  />
</template>

<script>
import { defineComponent } from 'vue'
import LineChart from './LineChart.vue'

export default defineComponent({
  name: 'MonthlyChartContainer',
  extends: LineChart,
  data () {
    return {
      state: {
        isLoaded: false,
        chartData: null
      }
    }
  },
  mounted () {
    this.state.isLoaded = false
    fetch('/api/userlist')
    .then((response) => response.json())
    .then((result) => {
      this.state.chartData = result
      this.state.isLoaded = false
    })
    .cath((err) => {
      console.error(err)
    })
  }
})
</script>

