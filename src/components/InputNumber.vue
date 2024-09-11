<template>
    <div class="input-number">
      <input 
        type="number" 
        :value="modelValue" 
        @input="updateValue" 
        placeholder="Número" 
      />
    </div>
  </template>
  
  <script>
  export default {
    props: {
      modelValue: {
        type: Number,
        required: true,
      },
    },
    methods: {
      updateValue(event) {
        this.$emit('update:modelValue', parseFloat(event.target.value));
      },
    },
  };
  </script>
  
  <style scoped>
  .input-number {
    margin: 10px;
  }
  </style>
  