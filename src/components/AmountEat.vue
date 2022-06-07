<template>
  <div id="amount">
    <input v-model.number="Nutrition_facts" type="number" /> /100 ×
  <input v-model.number="Foods_amount" type="number" /> = {{ result }}
  <!-- <p>
    <animated-integer :value="firstNumber"></animated-integer> + 
    <animated-integer :value="secondNumber"></animated-integer> =
    <animated-integer :value="result"></animated-integer>
  </p> -->
  </div>
</template>

<script>
import { defineComponent } from 'vue'
// import { gsap } from 'gsap'

export default defineComponent({
    name: 'AmountEat',
    data() {
        return {
            Nutrition_facts: 20,
            Foods_amount: 40
        }
    },
    computed: {
        result() {
            return this.Nutrition_facts/ 100 * this.Foods_amount
    }
    }
})

// amount.component('animated-integer', {
//     template: '<span>{{ fullValue }}</span>',
//     props: {
//         value: {
//             type: Number,
//             required: true
//         }
//     },
//     data() {
//         return {
//             tweeningValue: 0
//         }
//     },
//     computed: {
//         fullValue() {
//             return Math.floor(this.tweeningValue)
//         }
//     },
//     methods: {
//         tween(newValue) {
//             gsap.to(this.$data, {
//                 duration: 0.5,
//                 tweeningValue: newValue,
//                 ease: 'sine'
//             })
//         }
//     },
//     watch: {
//         value(newValue) {
//             this.tween(newValue)
//         }
//     },
//     mounted() {
//         this.tween(this.value, 0)
//     }
// })
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
