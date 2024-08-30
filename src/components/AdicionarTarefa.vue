<script setup>
const model = defineModel()
import ListarTarefas from './ListarTarefas.vue';
function adicionarTarefa(){
 adicionarTarefa.push(ListarTarefas) // gambiarra que deu errado
}
</script>

<template>
    <section>
        <h2>Adicione uma nova tarefa</h2>
        <input type="text" v-model="model" @keyup.enter="$emit('adicionarTarefa')" />
        <button @click="adicionarTarefa" >Adicionar</button>
    </section>
</template>

<style scoped>
input {
    width: 50%;
    padding: 5px;
    margin: 5px 0;
}

button {
    padding: 5px;
    margin: 5px 0;
}
</style>