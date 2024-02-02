<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: "+",
      resultado: 0,
    };

//O método data() é utilizado para definir os dados que serão utilizados no componente. Ele retorna um objeto contendo as propriedades numero1, numero2, operacao, e resultado, que são reativos. Isso significa que qualquer alteração nesses dados irá automaticamente refletir na interface do usuário.
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case "+":
          this.resultado = this.numero1 + this.numero2;
          break;
        case "-":
          this.resultado = this.numero1 - this.numero2;
          break;
        case "*":
          this.resultado = this.numero1 * this.numero2;
          break;
        case "/":
          this.resultado = this.numero1 / this.numero2;
          break;
        default:
          this.resultado = 0;

// Este método é chamado sempre que há uma mudança nos valores de numero1, numero2 ou operacao. Ele realiza o cálculo com base nos valores atuais dessas variáveis e atribui o resultado à propriedade resultado.
//A estrutura de controle switch é utilizada para determinar qual operação aritmética deve ser realizada com base no valor de operacao.
      }
    },
  },
};
</script>

<template>
  <div id="app" class="calculator-container mt-5" style="max-width: 500px;">
    <h1 class="mb-4">Calculadora Aritmética</h1>

    <div class="form-group">
      <label for="numero1">Número 1:</label>
      <input type="number" class="form-control" v-model="numero1" @input="calcular" />
    </div>

    <div class="form-group">
      <label for="numero2">Número 2:</label>
      <input type="number" class="form-control" v-model="numero2" @input="calcular" />
    </div>

    <div class="form-group">
      <label for="operacao">Operação:</label>
      <select class="form-control" v-model="operacao" @change="calcular">
        <option value="+">Soma (+)</option>
        <option value="-">Subtração (-)</option>
        <option value="*">Multiplicação (*)</option>
        <option value="/">Divisão (/)</option>
      </select>
    </div>

    <div class="form-group">
      <label for="resultado">Resultado:</label>
      <input type="text" class="form-control" v-model="resultado" readonly />
    </div>
  </div>
</template>

<style>
.calculator-container {
  background-color: #5e37ca;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  color: rgb(243, 248, 246);
}
</style>

