<template>
    <div class="container-card">
        <div class="card">
            <div class="form">

                <div class="form-control">
  <h2>Cadastro</h2>
</div>
                <div class="form-control">
                    <input type="hidden" v-model="tarefa.id">
                </div>
                <div class="form-control">
                    <label for="tarefa">Tarefa</label>
                </div>
                <div class="form-control">
                    <input-base id="tarefa" v-model="tarefa.nome" placeholder="Digite a tarefa" />
                </div>
                <div class="form-control">
                    <button-base class="primary" @acao="salvar" textoButton="salvar"></button-base>
                </div>
            </div>
        </div>
        <div class="card">
            <h1>To-do</h1>
            <table-custom :tarefasProps="tarefas" @settarefa="atualizar"></table-custom>
        </div>
    </div>
</template>
  
<script>

import InputBase from './InputBase.vue'
import ButtonBase from './ButtonBase.vue'
import TableCustom from './TableCustom.vue'
export default {
    name: 'App',
    components: {
        InputBase,
        ButtonBase,
        TableCustom
    },

    data() {
        return {
            tarefa: {},
            tarefas: [],
        }
    },

    methods: {
        salvar() {

            let index = this.tarefas.indexOf(this.tarefa);

            console.log(this.tarefa.nome)
            if (index === -1) {
                if (this.tarefa.nome == undefined) {
                    alert("error")
                } else {
                    this.tarefas.push(this.tarefa)
                }
            } else {
                this.tarefas[index] = this.tarefa
            }
            this.tarefa = {}
        },

        atualizar(tarefa) {
            this.tarefa = tarefa;
        }
    },
}
</script>
  
<style scoped>
.container-card {
    width: 100%;
    background:linear-gradient(to left, rgb(76, 178, 237), rgb(100, 198, 218));
    min-height: 100vh;
    display: flex;
    justify-content: center;
}

.container-card .card {
    width: 35%;
    /* background-color: rgb(9, 37, 22); */
    margin: 60px 2px 2px 2px;
    min-height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 5px;
    border: 1px solid white;
}

.container-card .card:nth-child(2) {
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
}

.container-card .card h1 {
    text-align: center;
    width: 100%;
    margin-bottom: 20px;
    color: white;
}

.container-card .card .form {
    width: 60%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color:white;
    height: 80%;
    border-radius: 5px;
    box-shadow: 1px 1px 5px gray;
}

.container-card .card .form .form-control {
    display: flex;
    padding: 3px;
    width: 80%;
}

.container-card .card .form .form-control:nth-child(4) {
    justify-content: center;
}

.container-card .card .form .form-control h2{
  width: 100%;
  text-align: center;
  color: gray;
}

.container-card .card .form .form-control label{
    color:gray;
    font-size: 14px;
}

@media (max-width: 800px) {
    .container-card {
        flex-direction: column;
    }

    .container-card .card {
        width: 100%;
        min-height: 100vh
    }

    .container-card .card:nth-child(2) {
        margin-top: 10px;
    }

    .container-card .card .form {
        padding: 30px 0px;
    }
}</style>
  