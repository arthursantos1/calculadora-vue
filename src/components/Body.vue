<script setup>
    const props = defineProps(['calculaResultado', 'estado']);
</script>

<template>
    <div class="container">
        <form class="mt-5">
            <label class="form-label fw-semibold">Primeiro Número:</label>
            <input type="number" placeholder="Digite o primeiro número" class="form-control" :value="props.estado.primeiroNumero"
                @keyup="evento => props.estado.primeiroNumero = evento.target.value">
            <label class="form-label mt-3 fw-semibold">Operação:</label>
            <select placeholder="Selecione uma operação" class="form-control" :value="props.estado.operacao" @change="evento => props.estado.operacao = evento.target.value">
                <option value="--">Selecione uma operação</option>
                <option value="somar">Adição (+)</option>
                <option value="subtrair">Subtração (-)</option>
                <option value="multiplicar">Multiplicação (x)</option>
                <option value="dividir">Divisão (/)</option>
            </select>
            <label class="form-label mt-3 fw-semibold">Segundo Número:</label>
            <input type="number" placeholder="Digite o segundo número" class="form-control" :value="props.estado.segundoNumero"
                @keyup="evento => props.estado.segundoNumero = evento.target.value">
            <div class="row mt-4">
                <div class="col">
                    <button type="reset" class="form-control text-bg-light btn-resetar">Limpar</button>
                </div>
            </div>
            <div class="mt-4 text-center">
                <h4 class="fw-semibold">Resultado da operação:</h4>
                <div class="container mt-4">
                    <h3>{{ props.calculaResultado }}</h3>
                </div>
            </div>
        </form>
    </div>
</template>


<style scoped>
.btn-resetar {
    background-image: linear-gradient(to right, rgb(68, 68, 237), purple);
    color: #fff;
}
</style>