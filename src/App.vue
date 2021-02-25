<template>
  <div id="app">
    <h2>Cadastro:</h2>
    <input type="text" placeholder="name" v-model="nameField"> <br>
    <p v-if="nameValidation == true">Nome inválido!</p>
    <input type="email" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="age" v-model="ageField"> <br>
    <button @click="userRegister">Cadastrar</button>
  
    <div v-for="(user, index) in users" :key="user.id">
      <h3>{{ index }}</h3>
      <Cliente :client="user" @meDelete="deleteUser($event)"/>
    </div>
  </div>
</template>

<script>
import Cliente from './components/Cliente';
//import Produto from './components/Produto';
export default {
  data(){
    return{
      nameField: "",
      emailField: "",
      ageField: "",
      nameValidation: false,
      users:[
        {
          id:1,

          name: "Leonardo",
          number:"(55)959219",
          email:"aiaigsagsaqe@gmail.com",
          age:20,
          description:"arroz doce"
        },
        {
          id:3,
          name: "Tiktok",
          number:"(20)5129219",
          email:"attttttt@gmail.com",
          age:30,
          description:"juvenal"
        },
        {
          id:10,
          name: "Vfsafastor",
          number:"(22)5114219",
          email:"aiairqwrwqpito@gmail.com",
          age:42,
          description:"TATIANE MEU AMOR"
        }
      ]
    }
  },
  name: 'App',
  components: {
    Cliente,
    //Produto
  },
  methods:{
    userRegister: function(){
      if(this.nameField == "" || this.nameField == " " || this.nameField < 3){
        console.log("erro de validação");
        this.nameValidation = true;
      }else{
        this.users.push({
        id:Date.now(),
        name:this.nameField,
        email: this.emailField,
        age: this.ageField
      })
      this.nameField = "";
      this.emailField = "";
      this.ageField = "";
      this.nameValidation = false;
      } //if user.id == id, he will be removed from the array
  
    },
    deleteUser: function($event){
      console.log("Recebendo evento!");
      var id = $event.userId;
      var newArray = this.users.filter(user => user.id != id); //if user.id is the same than id, he will be removed from the array
      this.users = newArray;
    }
  }

}
</script>

<style>

</style>
