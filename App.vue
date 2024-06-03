<script setup>
import { ref } from 'vue'

const num1 = ref("")
const num2 = ref("")
const product = ref(0)
const calculated = ref(false)

const calculateProduct = () => {
  product.value = Number(num1.value) * Number(num2.value)
  calculated.value = true
}


const reset = () => {
  num1.value = ""
  num2.value = ""
  product.value = 0
  calculated.value = false
}
</script>

<template>
  <div class=""container>
    <h1>Compute Product</h1>
    <div class="input-container">
      <label for="num1">Number 1:</label>
      <input id="num1" v-model="num1" type="number"/>
    </div>
    <div class="input-container">
      <label for="num2">Number 2:</label>
      <input id="num2" v-model="num2" type="number"/>
    </div>

    <button v-if="!calculated" @click="calculateProduct">Submit</button>

    <div v-if="calculated">
      <p>Product is: {{ product }}</p>
      <button @click="reset">Reset</button>
    </div>
  </div>
</template>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-image: url('C:\Users\rites\OneDrive\Pictures\Actor.png');
  background-size: cover;
  background-position: center;
}

.input-container {
  margin-bottom: 10px;
}
.input-container label {
  margin-right: 10px;
}
</style>
