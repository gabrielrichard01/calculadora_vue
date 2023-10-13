
<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0
    };
  },
  methods: {
    calcularResultado() {
      const num1 = parseFloat(this.numero1);
      const num2 = parseFloat(this.numero2);

      switch (this.operacao) {
        case 'soma':
          this.resultado = num1 + num2;
          break;
        case 'subtracao':
          this.resultado = num1 - num2;
          break;
        case 'multiplicacao':
          this.resultado = num1 * num2;
          break;
        case 'divisao':
          this.resultado = num2 !== 0 ? num1 / num2 : 'Não é possível dividir por zero';
          break;
        default:
          this.resultado = 'Operação inválida';
      }
    }
  }
};
</script>

<template>
  <div class="container">
    <div class="calculadora">
      <input v-model="numero1" type="number" placeholder="Número 1" @input="calcularResultado">
      <select v-model="operacao" @change="calcularResultado">
        <option value="soma">Soma (+)</option>
        <option value="subtracao">Subtração (-)</option>
        <option value="multiplicacao">Multiplicação (*)</option>
        <option value="divisao">Divisão (/)</option>
      </select>
      <input v-model="numero2" type="number" placeholder="Número 2" @input="calcularResultado">
      <p>Resultado: {{ resultado }}</p>
    </div>
  </div>
</template>

<style scoped>
  .body{
    background-color: blue;
  }
  .container{
    max-width: 600px;
    margin: 0 auto;
    text-align: center;
  }

  .calculadora{
    position: absolute;
    top: 40vh;
  }

  input, select{
    padding: 8px;
    width: 25%;
    text-align: center;
    font-weight: bold;
    margin-left: 15px;
  }

  p{
    font-size: 30px;
    font-family: Arial, Helvetica, sans-serif;
    font-weight: bolder;
    color: green;
  }
</style>