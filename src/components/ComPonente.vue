<template>
    <div :class="{'clientes': !isPremium,'clientes-premium': isPremium}" >
        <hr>
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>Email: {{cliente.email}}</p>
        <p v-if = "showIdade===true"  >idade: {{cliente.idade}}</p>
        
      
        
        <button @click="mudarCor($event)">MUDAR COR</button>


       
    </div>
</template>

<script>
export default {
    data(){ 
        return{
            isPremium: false

            
        }
    },
    props: {
        
        cliente: Object,
        showIdade: Boolean



    },
    methods: {
        mudarCor: function($event){
            console.log($event)
                this.isPremium = !this.isPremium;
        }
    }
        

}
</script>

<style scoped>
    .clientes{
        
        color:blue;
        background-color: gold; 
        padding: 50px;
        max-height: 300px;
        width: 300px;
        margin-top: 5px;
       
    }

    .clientes-premium{
        color: yellow;
        background-color: black;
        padding: 50px;
        max-height: 300px;
        width: 300px;
        margin-top: 5px;
    }

</style>
