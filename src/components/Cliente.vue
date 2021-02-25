<template>
    <div :class="{'client': !isPremium, 'client-premium': isPremium}">
        <h4>Name: {{client.name}}</h4>
        <p>Description: {{client.description }}</p>
        <p>Number: {{client.number}}</p>
        <p>Email: {{client.email | processEmail()}}</p>
        <p v-if="showAge == true">Age: {{client.age}}</p>
        <p v-else> O usuário não tem idade, é doido</p>

        <button @click="changeColor($event)">Mudar cor!</button>
        <button @click="sendDeleteEvent()">Deletar</button>

        <h4>special id: {{idSpecial}}</h4>
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
        },
        sendDeleteEvent: function(){
            console.log("Emitindo do filho");
            this.$emit("meDelete", {userId:this.client.id, component: this});
        },
        tiktok:function(){
            console.log("tiktok");
        }
    },
    filters:{
        processEmail: function(value){
            return value.toUpperCase();
        }
    },
    computed:{
        idSpecial: function (){
            return (this.client.name + this.client.email).toUpperCase();
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