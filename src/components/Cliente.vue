<template>
    <div id="cliente">
        <h2>Aluno: {{ nome }}</h2>
        <h2>Descrição do cliente: {{descricao}}</h2>
        <h3>fsfsfs</h3>
        <hr>
        <input type="text" :value="nome">
        <hr>
        <input type="text" :value="descricao">
    </div>
    
</template>

<script>
export default {
    data(){
        return{
            nome: "Hey",
            numero: "",
            email: "",
            idade: 0,
            descricao: "Lorem ipsum Lorem Ipsum"
        }
    }
}
</script>

<style scoped>
    #cliente{
        color:blue;
        background:linear-gradient(to bottom, rgba(114, 113, 113,0.9), rgba(114, 113, 113,0.7),rgba(114, 113, 113,0.5))
    }
</style>