<script setup>
import { reactive, computed } from 'vue';

const estado = reactive({
    numero1: 0,
    numero2: 0,
    operacao: '+',
});

const calcularResultado = computed(() => {
    const { numero1, numero2, operacao } = estado;

    switch (operacao) {
        case '+':
            return parseFloat(numero1) + parseFloat(numero2);
        case '-':
            return parseFloat(numero1) - parseFloat(numero2);
        case '*':
            return parseFloat(numero1) * parseFloat(numero2);
        case '/':
            return numero2 != 0 ? parseFloat(numero1) / parseFloat(numero2) : 'Erro: Divisão por zero';
        default:
            return 'Operação inválida';
    }
});
</script>

<template>
    <div>
        <div class="form-group">
            <label for="numero1">Número 1:</label>
            <input type="number" id="numero1" v-model.number="estado.numero1" class="form-control" />
        </div>

        <div class="form-group">
            <label for="numero2">Número 2:</label>
            <input type="number" id="numero2" v-model.number="estado.numero2" class="form-control" />
        </div>

        <div class="form-group">
            <label for="operacao">Operação:</label>
            <select id="operacao" v-model="estado.operacao" class="form-control">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
        </div>

        <div class="resultado">
            <h3>Resultado: {{ calcularResultado }}</h3>
        </div>
    </div>
</template>

<style scoped>
.form-group {
    margin-bottom: 15px;
}

.form-control {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border: 1px solid #ddd;
    border-radius: 5px;
    box-sizing: border-box;
}

.resultado {
    margin-top: 20px;
    font-size: 1.5em;
    color: #333;
}
</style>
