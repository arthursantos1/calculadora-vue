<template>
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
</style>