<script setup>
import { reactive, ref } from 'vue';

/* const estado = reactive({
  primeiroNumero: '',
  segundoNumero: '',
}) */

const primeiroNumero = ref('');
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
        <input type="number" placeholder="Digite o primeiro número" class="form-control" v-model="primeiroNumero">
        <label class="form-label mt-3 fw-semibold">Operação:</label>
        <select name="" id="" placeholder="Selecione uma operação" class="form-control">
          <option selected>Selecione uma operação</option>
          <option value="1">Adição (+)</option>
          <option value="2">Subtração (-)</option>
          <option value="3">Multiplicação (x)</option>
          <option value="4">Divisão (/)</option>
        </select>
        <label class="form-label mt-3 fw-semibold">Segundo Número:</label>
        <input type="number" placeholder="Digite o segundo número" class="form-control">
        <div class="row mt-4">
          <div class="col-9">
            <button type="button" class="form-control btn-calcular">Calcular</button>
          </div>
          <div class="col">
            <button type="reset" class="form-control text-bg-light">Limpar</button>
          </div>
        </div>
        <div class="mt-3">
        <p class="fw-semibold">Resultado da operação:</p>
        <i>{{ primeiroNumero }}</i>
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

.btn-calcular {
  background-image: linear-gradient(to right, rgb(68, 68, 237), purple);
  color: #fff;
}
</style>
