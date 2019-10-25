<template>
  <div class="container">
    <h1 class="text-center">Animais Vue js</h1>

    <div class="row">

      <div v-for = "foto in fotos" class="col-12 col-md-4  mb-3" >
        
        <meu-painel :titulo="foto.titulo">
          <img class="rounded card-img-top" :src="foto.url" :alt="foto.titulo">
        </meu-painel>

      </div>
    </div>

  </div>
</template>

<script>
import Painel from "./components/shared/painel/Painel.vue";

export default {

  components:{
    "meu-painel":Painel
  },

  data(){
    return{
      fotos:[]
    }
  },


  created(){
    //alert("Criei o componente");
    let promise = this.$http.get("http://localhost:3000/v1/fotos");
    promise
      .then(res => res.json())
      .then(fotos => this.fotos = fotos, err => console.log(err))

  }
}

</script>

<style>
  img{
    height: 200px;
    width: 300px;
  }

  .borda-cor-especial{
    border-color: darkred;
  }

</style>
