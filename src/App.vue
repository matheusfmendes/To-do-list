<template>
  <div class="h-fit pb-20 m-auto mt-[20vh] w-3/4 bg-slate-600">
    <h1 class="text-center text-2xl text-white py-10">Lista de afazeres</h1>
    <div class="flex flex-row w-[80%] my-4 py-6 bg-slate-800 m-auto">
      <input v-model="tarefa.description" class="flex-1 rounded-md px-2 py-2 mx-2 bg-slate-900 text-white self-center" placeholder="Adicionar tarefa..."/>
      <button class="flex-2 rounded-md px-2 py-2 text-white bg-slate-600 mx-2 self-center" @click="addTarefa">Adicionar tarefa</button>
    </div>
    <div class="flex flex-col">
      <div v-for="(t, index) in tarefas" :key="index" class="flex flex-row w-[80%] my-4 bg-slate-800 m-auto">
        <p class="px-6 py-4 text-white text-md justify-center">{{ t.description }}</p>
        <button class="px-5 rounded-md py-2 bg-slate-600 mx-2 self-center ml-auto text-white" @click="toggleTarefa(t)">{{ t.checked ? 'Editar' : 'Concluido' }}</button>
        <button class="px-5 rounded-md  py-2 bg-slate-600 mx-2 self-center ml-2 text-white" @click="removeTarefa(t)">Remover</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tarefas: [
        { description: 'Cafe da manha', checked: false },
        { description: 'Almoco', checked: false },
        { description: 'Jantar', checked: false },
      ],
      tarefa: { description: '', checked: false }
    }
  },
  methods: {
    addTarefa() {
      if (this.tarefa.description.trim() !== '') {
        const novaTarefa = { ...this.tarefa };

        this.tarefas.push(novaTarefa);
        this.tarefa.description = '';
      }
    },

    removeTarefa(tarefa) {
      const index = this.tarefas.findIndex(item => item.description === tarefa.description);
      if (index > -1) {
        this.tarefas.splice(index, 1);
      }
    },

    toggleTarefa(tarefa) {
      const index = this.tarefas.findIndex(item => item.description === tarefa.description);
      if (index > -1) {
        if (tarefa.checked) {
          const novaDescricao = prompt('Insira a nova descrição da tarefa', tarefa.description);

          if (novaDescricao !== null) {
            this.tarefas[index].description = novaDescricao;
            console.log('Tarefa editada:', tarefa);
          }
        } else {
          this.tarefas[index].checked = true;
          console.log('Tarefa concluída:', tarefa);
        }
      }
    }
  }
}
</script>

<style>
@import './assets/style.css';

</style>
