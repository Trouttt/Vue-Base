<template>
    <div id="cliente">
        <h4>Name: {{client.name}}</h4>
        <p>Description: {{client.description}}</p>
        <p>Number: {{client.number}}</p>
        <p>Email: {{client.email}}</p>
        <p v-if="showAge == true">Age: {{client.age}}</p>
        <p v-else-if="showAge == false"></p>
        <p v-else> O usuário não tem idade, é doido</p>
    </div>
    
</template>

<script>
export default {
    props: {
        client:Object,
        showAge: Boolean
    }
}
</script>

<style scoped>
    #cliente{
        color:blue;
        background-color:#ECE5E3;
        padding:1vw;
        margin-bottom:1vw;
    }
</style>