<template>
  <hello-world />
  <steppers msg="steppers"/>
  <amount-eat msg="amount-eat"/>
  <dietary-intake msg="dietary-intake"/>
  <stack-chart :chartData=state.chartData :chartOptions=state.chartOptions :styles="{'display':'flex', 'justify-content':'center'}" />

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Steppers from './components/Steppers.vue'
import AmountEat from './components/AmountEat.vue'
import DietaryIntake from './components/DietaryIntake.vue' 
import StackChart from './components/StackChart.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Steppers,
    AmountEat,
    DietaryIntake,
    StackChart,
  },
}
</script>