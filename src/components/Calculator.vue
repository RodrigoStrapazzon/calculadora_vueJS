<template>
    <div class="calculator">
      <h1>Calculadora Aritmética</h1>
  
      <InputNumber v-model="num1" />
  
      <InputNumber v-model="num2" />
  
      <OperationSelect v-model="operation" />
  
      <h2>Resultado: {{ result }}</h2>
    </div>
  </template>
  
  <script>
  import InputNumber from './InputNumber.vue';
  import OperationSelect from './OperationSelect.vue';
  
  export default {
    components: {
      InputNumber,
      OperationSelect,
    },
    data() {
      return {
        num1: 0,
        num2: 0,
        operation: 'add', // Operação padrão
      };
    },
    computed: {
      result() {
        switch (this.operation) {
          case 'add':
            return this.num1 + this.num2;
          case 'subtract':
            return this.num1 - this.num2;
          case 'multiply':
            return this.num1 * this.num2;
          case 'divide':
            return this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
          default:
            return 0;
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .calculator {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: center;
  }
  
  h2 {
    margin-top: 20px;
    color: #333;
  }
  </style>
  