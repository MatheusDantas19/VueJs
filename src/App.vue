<template>
  <div class="container">
    <h1 class="text-center">OI</h1>
    <div class="row">
      <div v-for = "foto in fotos" class="col-12 col-md-4">
        <img class="rounded" :src="foto.url" :alt="foto.titulo">      
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      titulo:"Gta 5",
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


</style>
