<!-- app.vue -->
<template>
  <div id="app">
    <input v-model="num1" type="number" @input="calcular" class="input-field">
    <select v-model="operador" @change="calcular" class="select-field">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model="num2" type="number" @input="calcular" class="input-field">

    <p class="resultado">Resultado: {{ resultado }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operador: '+',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      switch (this.operador) {
        case '+':
          this.resultado = this.num1 + this.num2;
          break;
        case '-':
          this.resultado = this.num1 - this.num2;
          break;
        case '*':
          this.resultado = this.num1 * this.num2;
          break;
        case '/':
          this.resultado = this.num1 / this.num2;
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>

<style scoped>
#app {
  max-width: 400px;
  margin: 50px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  background-color: #f0f0f0;
}

.input-field, .select-field, .resultado {
  margin-bottom: 10px;
}

.input-field, .select-field {
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 3px;
}

.select-field {
  width: 100%;
}

.resultado {
  font-weight: bold;
  color: #333;
}
</style>
