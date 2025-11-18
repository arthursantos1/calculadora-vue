<script setup>
import { reactive } from 'vue';

const estado = reactive({
  primeiroNumero: '',
  segundoNumero: '',
  operacao: '-',
})

function calculaResultado() {
  const { primeiroNumero, segundoNumero, operacao } = estado;

  switch (operacao) {
    case 'somar':
      return parseFloat(primeiroNumero) + parseFloat(segundoNumero);
    case 'subtrair':
      return primeiroNumero - segundoNumero;
    case 'multiplicar':
      return primeiroNumero * segundoNumero;
    case 'dividir':
      if (segundoNumero == 0) {
        return 'Não é possível dividir o número por Zero'
      } else {
        return primeiroNumero / segundoNumero;
      }
    default:
      return 'Selecione uma das operações';
  }
}
</script>

<template>
  <div class="container">
    <div class="text-center mt-3">
      <h1 class="text-color fs-2">Calculadora Aritmética</h1>
      <p class="fs-6">Realize operações matemáticas básicas de forma rápida e fácil. Digite os números, escolha a
        operação e obtenha o resultado instantaneamente.</p>
    </div>
    <header class="p-2 mt-5 d-flex">
      <div class="px-3">
        <i class="bi bi-calculator" style="font-size: 30px;"></i>
      </div>
      <div>
        <p>Calculadora</p>
        <p>Realize suas operações matemáticas</p>
      </div>
    </header>
    <div class="container">
      <form class="mt-5">
        <label class="form-label fw-semibold">Primeiro Número:</label>
        <input type="number" placeholder="Digite o primeiro número" class="form-control" @keyup="evento => estado.primeiroNumero = evento.target.value">
        <label class="form-label mt-3 fw-semibold">Operação:</label>
        <select placeholder="Selecione uma operação" class="form-control" @change="evento => estado.operacao = evento.target.value">
          <option selected>Selecione uma operação</option>
          <option value="somar">Adição (+)</option>
          <option value="subtrair">Subtração (-)</option>
          <option value="multiplicar">Multiplicação (x)</option>
          <option value="dividir">Divisão (/)</option>
        </select>
        <label class="form-label mt-3 fw-semibold">Segundo Número:</label>
        <input type="number" placeholder="Digite o segundo número" class="form-control" @keyup="evento => estado.segundoNumero = evento.target.value">
        <div class="row mt-4">
          <div class="col">
            <button type="reset" class="form-control text-bg-light btn-resetar">Limpar</button>
          </div>
        </div>
        <div class="mt-4 text-center">
          <h4 class="fw-semibold">Resultado da operação:</h4>
          <div class="container mt-4">
            <p>{{ calculaResultado() }}</p>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.text-color {
  background-image: linear-gradient(to right, #8972fc, #7043fb);
  background-clip: text;
  color: transparent;
}

header {
  background-image: linear-gradient(to right, rgb(68, 68, 237), purple);
  border-radius: 5px;
}

header p {
  color: #fff;
  margin: 0;
}

header i {
  background-color: #ffffff23;
  border-radius: 3px;
  color: white;
  width: 30px;
}

.btn-resetar {
  background-image: linear-gradient(to right, rgb(68, 68, 237), purple);
  color: #fff;
}
</style>
