<template>
    <div :class="{'client': !isPremium, 'client-premium': isPremium}">
        <h4>Name: {{client.name}}</h4>
        <p>Description: {{client.description}}</p>
        <p>Number: {{client.number}}</p>
        <p>Email: {{client.email}}</p>
        <p v-if="showAge == true">Age: {{client.age}}</p>
        <p v-else> O usuário não tem idade, é doido</p>

        <button @click="changeColor($event)">Mudar cor!</button>

    </div>
    
</template>

<script>
export default {
    data(){
        return{
            isPremium: true
        }
    },
    props: {
        client:Object,
        showAge: Boolean
    },
    methods:{
        changeColor: function($event){
            console.log($event); 
            this.isPremium = !this.isPremium;
        }
    }
}
</script>

<style scoped>
    .client{
        color:blue;
        background-color:#ECE5E3;
        padding:1vw;
        margin-bottom:1vw;
    }

    .client-premium{
        background-color:black;
        color:yellow;
        padding:1vw;
        margin-bottom:1vw;
    }
</style>