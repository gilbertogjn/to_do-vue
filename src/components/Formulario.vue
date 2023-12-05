<script setup>
    const props = defineProps(['cadastrarTarefa', 'tarefaTemp', 'trocarFiltro', 'editaTarefaTemp'])
</script>

<template>
    <form @submit.prevent="props.cadastrarTarefa">
        <div class="row">
            <div class="col">
                <input required :value="props.tarefaTemp" @change="props.editaTarefaTemp"
                    class="form-control" type="text" placeholder="Digite aqui a descrição da tarefa">
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn btn-primary">
                    Cadastrar
                </button>
            </div>
            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="form-control">
                    <option value="todas">Todas tarefas</option>
                    <option value="pendentes">Pendentes</option>
                    <option value="finalizadas">Finaliadas</option>
                </select>
            </div>
        </div>
    </form>
</template>