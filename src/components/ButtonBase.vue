<template>
    <button class="btn"  @click="submit()">{{ textoButton }}</button>
</template>
<script>
export default {

    props: {
        textoButton:{
            type:String
        },

        estilo:{
            type:String
        }
    },

    methods: {
        submit() {
            this.$emit('acao');
        }
    }
}
</script>
<style scoped>
.btn {
    border: none;
    outline: none;
    height: 30px;
    border-radius: 5px;
    padding: 5px;
    color: white;
    margin-left: 2px;
    cursor: pointer;
    transition: all 0.5s;
}

.primary{
    background-color:#007bff;
}

.primary:hover{
    box-shadow: 1px 1px 2px rgb(65, 48, 226);
}

.danger {
    background-color: #dc3545;
}

.danger:hover{
    box-shadow: 1px 1px 2px rgb(230, 148, 6);
}

.sucess {
    background-color: #28a745
}

.sucess:hover{
    box-shadow: 1px 1px 2px rgb(49, 111, 7);
}
</style>