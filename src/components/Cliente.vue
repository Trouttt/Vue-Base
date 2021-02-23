<template>
    <div id="cliente">
        <h4>Name: {{client.name}}</h4>
        <p>Description: {{client.description}}</p>
        <p>Number: {{client.number}}</p>
        <p>Email: {{client.email}}</p>
        <p>Age: {{client.age}}</p>
    </div>
    
</template>

<script>
export default {
    props: {
        client:Object
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