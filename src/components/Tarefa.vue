<template>
    <div class="tile flex-centered" :class="{ checked: tarefa.checked }">
        <div class="tile-content">
            <div class="tile-subtitle">{{ tarefa.description }}</div>
        </div>
        <div class="tile-action">
            <button @click="$emit('toggle', tarefa)"
                :class="tarefa.checked">
                <span v-if="tarefa.checked">Desmarcar</span>
                <span v-else>Concluir</span>
            </button>

            <button class="px-5 py-2 border h-fit border-white self-center text-black remover-button"
                @click="$emit('remove', tarefa)">
                Remover
            </button>

            <button class="px-5 py-2 border h-fit border-white self-center text-black editar-button"
                @click="$emit('edit', tarefa)">
                Editar
            </button>
        </div>
    </div>
</template>

<script>
export default {
    name: "TarefaItem",
    props: {
        tarefa: { type: Object, required: true }
    }
};
</script>


<style scoped>
.checked {
    text-decoration: line-through;
    color: lightgray;
}
</style>

