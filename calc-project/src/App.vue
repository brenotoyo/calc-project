<script setup>
    import { reactive, computed } from 'vue';
    import Cabecalho from './components/Cabecalho.vue';
    import CamposCalc from './components/Campos-calc.vue';

    const estado = reactive ({
        numeroA: null,
        numeroB: null,
        operacao: '+',
    })

    const resultado = computed(() => {
        const a = Number(estado.numeroA);
        const b = Number(estado.numeroB);

        if (estado.numeroA === null || estado.numeroB === null) {
            return 'Escolha 2 números!';
        }

        if (estado.operacao === '/' && a === 0) {
            return 'Zero não é divisível!';
        }

        if (estado.operacao === '/' && b === 0) {
            return 'Divisão por zero!';
        }

        switch (estado.operacao) {
            case '+': return a + b;
            case '-': return a - b;
            case '*': return a * b;
            case '/': return a / b;
            default:  return 'Operação inválida';
        }
    });
</script>

<template>
    <div class="container">
        <Cabecalho />
        <CamposCalc :escolherNumeroA="evento => estado.numeroA = evento.target.value"
                    :escolherNumeroB="evento => estado.numeroB = evento.target.value"
                    :escolherOperacao="evento => estado.operacao = evento.target.value" 
        />
        <div class="mt-4 -4 bg-ligh rounded-4">
            <h4>Resultado: <strong>{{ resultado }}</strong></h4>
        </div>
    </div>
</template>

<style scoped>

</style>
