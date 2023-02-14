<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
    <ul class=" mt-3 list-group">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                type="checkbox" name="" id="" :id="tarefa.titulo">
            <label :id="tarefa.titulo" :class="{ done: tarefa.finalizada }" class="ms-4" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>