<template>
  
  <div id="app">
      <h1>correios</h1>
      <hr>
      <h3>CADASTRO:</h3>
      <input type="text" placeholder="nome" v-model="nomeField"> <br> 
      <input type="email" placeholder="email" v-model="emailField"> <br>
      <input type="number" placeholder="idade" v-model="idadeField"><br>
      <button @click="cadastrarUsuario">Cadastrar</button>
      <div v-for="(cliente,index) in clientes" :key ="cliente.id">
         <h4>{{index+1}}</h4>
         <Cliente :cliente="cliente"/>

        </div>

      

   </div>    
       
      
       

</template>

<script>
import Cliente from './components/ComPonente.vue'




export default {
  name: 'App',
  data(){
    return {
      nomeField:"",
      emailField:"",
      idadeField:0,
      
      
      clientes: [
        {
         id: 88,
         nome: "salamandra",
         email: "salamandra@hotmail.com",
         idade: 93
        },
        {
         id: 38,
         nome: "dfsdf",
         email: "fsdfs@hotmail.com",
         idade: 43
        },
        {
         id: 33,
         nome: "dfsdf",
         email: "fsdfs@hotmail.com",
         
        },
      ]
    }
  },
  components: {
    Cliente,
    
  },
  methods: {
    cadastrarUsuario: function(){
      this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.idadeField, id: Date})  
      this.nomeField = "";
      this.emailField = "";
      this.idadeField = 0; 
}
},
}
</script>

<style>


#app {
  
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: blue;
  
  margin-bottom: 60px;
  margin-top: -10px;
}
</style>
