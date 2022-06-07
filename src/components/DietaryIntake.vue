<template>
  <div id="dietaryIntake">
    ( <input v-model.number="age" type="number" /> ,
  <input v-model.number="sex" type="number" /> ) = {{ result }}
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
    name: 'DietaryIntake',
    data() {
        return {
            age: 0,
            sex: 25
        }
    },
    computed: {
        result() {
            return this.age * this.sex
            // return Dietary[0][25]
    }
    }
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
