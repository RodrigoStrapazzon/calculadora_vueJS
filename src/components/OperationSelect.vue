<template>
  <div class="operation-select">
    <select :value="modelValue" @change="updateOperation">
      <option value="add">Adicionar (+)</option>
      <option value="subtract">Subtrair (-)</option>
      <option value="multiply">Multiplicar (*)</option>
      <option value="divide">Dividir (/)</option>
    </select>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: {
      type: String,
      required: true,
    },
  },
  methods: {
    updateOperation(event) {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>

<style scoped>
.operation-select {
  margin: 10px;
}
</style>
