<script>
// import { defineComponent } from 'vue'
import { Vue } from 'vue'
import { Bar } from 'vue3-chart-v2'

const StackChartBase = {
    extends: Bar,
    props: {
        chartData: {
            type: Object,
            required: true
        },
        chartOptions: {
            type: Object,
            required: false
        }},
    mounted () {
    // Overwriting base render method with actual data.
    this.renderChart(this.chartData, this.chartOptions)}
    // mounted() {},
//   コンポーネントが含む VNode に更新が行われる前に呼び出されます。
    // vnode
// el にて受け取った実際の DOM 要素の blueprint を表します。
// el
// ディレクティブがバインドされる要素。これを利用することで、 DOM を直接操作できます。https://v3.ja.vuejs.org/guide/custom-directive.html#%E5%9F%BA%E6%9C%AC
}


const StackChart = {
    extends: StackChartBase,
    data () {
    return {
      state: {
        chartData: {},
        chartOptions: {
          responsive: false,
          title: {
                display: true,
                fontSize: 20,
                text: "積上げ棒グラフ"
          },
          legend: {
                position: 'bottom'
          },                
          scales: {
                xAxes: [
                    {
                        stacked: true  // 積み上げの指定
                    }
                ],
                yAxes: [
                    {
                        stacked: true  //  積み上げの指定
                    }
                ]
          }
        }
      }
    }
  },
  beforeMount () {
    this.fillData()
  },
  methods: {
    fillData () {
      this.state.chartData = {
        labels: ['Label 1', 'Label 2'],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: [this.getRandomInt(), this.getRandomInt()]
          }
        ]
      }
    },
    getRandomInt () {
      return Math.floor(60)
    }
  }
//   ,mounted () {
//     // Overwriting base render method with actual data.
//     this.renderChart(this.chartData, this.Options)}
}

Vue.createApp(StackChart).mount('#app')
</script>

<style scope>

</style>


// https://www.isoroot.jp/blog/3524/
// https://github.com/chartjs/chartjs-plugin-annotation/issues/276
// chart参考