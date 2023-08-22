<template>
  <div class="calculator">
    <h1 class="title">Calculadora Aritmética</h1>
    <input v-model="num1" @input="calculate" class="input" type="number" />
    <select v-model="operator" @input="calculate" class="input">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model="num2" @input="calculate" class="input" type="number" />
    <button @click="calculate" class="calculate-button">Calcular</button>
    <div class="result">Resultado: {{ calculateResult }}</div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const operator = ref('+');
const result = ref(null);

const calculate = () => {
  switch (operator.value) {
    case '+':
      result.value = num1.value + num2.value;
      break;
    case '-':
      result.value = num1.value - num2.value;
      break;
    case '*':
      result.value = num1.value * num2.value;
      break;
    case '/':
      result.value = num1.value / num2.value;
      break;
    default:
      result.value = null;
  }
};

const calculateResult = computed(() => result.value);
</script>

<style scoped>
.calculator {
  display: grid;
  grid-template-columns: 1fr;
  gap: 10px;
  align-items: center;
  justify-content: center;
  text-align: center;
  width: 300px;
  margin: 0 auto;
}

.title {
  font-size: 24px;
  color: #333;
  margin-bottom: 20px;
}

.input {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
  text-align: center;
}

.calculate-button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

.result {
  margin-top: 20px;
  font-size: 18px;
  font-weight: bold;
  color: #333;
}
</style>
