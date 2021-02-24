<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <input type="text" v-model="user.name"/>
    <div v-for="(user, index) in users" :key="user.id">
      <h3>{{ index }}</h3>
      <Cliente :client="user"/>
    </div>
  </div>
</template>

<script>
import Cliente from './components/Cliente';
//import Produto from './components/Produto';
export default {
  data(){
    return{
      nomeDoVictor: "Victor Limaa",
      user:{
        name: "Victor",
        number:"(22)5129219",
        email:"fsafsito@gmail.com",
        age:12,
        description:"eita maluco doideira"
      },
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
  }

}
</script>

<style>

</style>
