<script setup>
import AdicionarTarefa from './AdicionarTarefa.vue';
const tarefas = [];


defineProps({
    realizadas: {
        type: Boolean,
        default: false
    }
})

// foi mal sor essa nao consigui fazer nada sla que deu comigo deve ser so um dia ruin
</script>

<template>
    <section v-for="tarefa in tarefas" :key="tarefa.id" :class="{ 'feita': tarefa.feita }"
        @click="$emit('click', tarefa.id)">
        <Transition name="fade">
            <p v-if="realizadas ? tarefa.feita : !tarefa.feita">{{ tarefa.descricao }}</p>
        </Transition>
    </section>
 
</template>

<style scoped>
.feita {
    text-decoration: line-through;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 2s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>