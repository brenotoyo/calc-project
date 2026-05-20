<script setup>
    const props = defineProps(['escolherNumeroA', 'escolherNumeroB', 'escolherOperacao']);
</script>

<template>
    <form>
        <div class="row">
            <div class="col-md-2">
                <label class="form-label">Número A: </label>
                <input @keyup="props.escolherNumeroA" class="form-control" type="number" placeholder="0">
            </div>
            <div class="col-md-2">
                <label class="form-label">Número B: </label>
                <input @keyup="props.escolherNumeroB" class="form-control" type="number" placeholder="0">
            </div>
            <div class="col-md-2">
                <label class="form-label">Operação: </label>
                <select @change="props.escolherOperacao" class="form-select">
                    <option value="+">Adição</option>
                    <option value="-">Subtração</option>
                    <option value="*">Multiplicação</option>
                    <option value="/">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>