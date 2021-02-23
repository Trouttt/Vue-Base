<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <input type="text" v-model="user.name"/>
    <Cliente :client="user"/>
    <Cliente :client="user"/>
    <Cliente :client="user"/>
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
        email:"aiaipapito@gmail.com",
        age:12,
        description:"eita maluco doideira"
      }
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
