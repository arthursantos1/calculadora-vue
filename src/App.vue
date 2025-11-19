<script setup>
import { reactive } from 'vue';
import Header from './components/header.vue';
import Body from './components/body.vue';

const estado = reactive({
  primeiroNumero: '',
  segundoNumero: '',
  operacao: '--',
})

function calculaResultado() {
  const { primeiroNumero, segundoNumero, operacao } = estado;

  switch (operacao) {
    case '--':
      return 'Selecione uma operação';
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
      return 'Selecione uma operação';
  }
}
</script>

<template>
  <div class="container">
    <Header />
    <Body :calcula-resultado="calculaResultado()" :estado="estado"/>
  </div>
</template>