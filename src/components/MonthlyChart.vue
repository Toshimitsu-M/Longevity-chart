<script>
import { defineComponent } from 'vue'
import { Pie } from 'vue3-chart-v2'

export default defineComponent({
  name: 'MonthlyChart',
  extends: Pie,
  props:{
    chartData: {
      type: Object,
      required: true
    },
    chartOptions: {
       type: Object,
       required: false
    },
  },mounted () {
    // Overwriting base render method with actual data.
    this.renderChart(this.chartData, this.chartOptions)
  },
})
</script>

