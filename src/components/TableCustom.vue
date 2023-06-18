<template>
    <div class="search">
        <label>Buscar</label>
        <input-base v-model="search" placeholder="Pesquise por tarefas"/>
    </div>

    <div class="list" v-for="tarefa, index of filtrarTarefas" :key="index">

        <div>
            <p>{{ tarefa.nome }}</p>
        </div>
        <div>
            <button-base class="danger" @acao="remover(index)" textoButton="remover" />
            <button-base class="sucess" @acao="editar(tarefa)" textoButton="editar" />
        </div>
    </div>
</template>
<script>
import ButtonBase from './ButtonBase.vue'
import InputBase from './InputBase.vue'
export default {

    components: {
        ButtonBase,
        InputBase
    },

    props: {
        tarefasProps: {},
    },

    data() {
        return {
            tarefa: {},
            tarefas: [],
            search: ""
        }
    },

    created() {
        this.tarefas = this.tarefasProps
    },

    methods: {
        remover(index) {
            if (index > -1) {
                this.tarefas.splice(index, 1);
            }
        },

        editar(tarefa) {
            this.$emit('settarefa', tarefa);
        },
    },

    computed: {
        filtrarTarefas() {

            let valores = this.tarefas;
            if (this.search != "" && this.search) {
                valores = this.tarefas.filter((tarefa) => {
                    return tarefa.nome.toUpperCase().includes(this.search.toUpperCase());
                });
            }
            return valores;
        }
    }

}
</script>

<style scoped>
.card .search {
    margin-bottom: 5px;
    width: 80%;
}

.card .list {
    background-color: rgb(6, 9, 37);
    width: 80%;
    border-radius: 5px;
    display: flex;
    padding: 10px;
    justify-content: space-between;
    margin-bottom: 5px;
    align-items: center;
}

p {
    color: white;
}
</style>

