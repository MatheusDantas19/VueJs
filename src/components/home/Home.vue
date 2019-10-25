<template>
  <section>
      <h1 class="text-center">Animais Vue js</h1> 
      <input type="seach" v-on:input="filtro = $event.target.value" placeholder="Filtre por parte do título" class="filtro" > 
      <article class="container bg-light">
          <div class="row justify-content-center">
              <div v-for="foto in fotosComFiltro">
                  <meu-painel :titulo="foto.titulo">
                      <imagem :titulo="foto.titulo" :url="foto.url"></imagem>
                    </meu-painel>
                </div>
            </div>
      </article>
  </section>
</template>

<script>
import Painel from "../shared/painel/Painel";
import ImagemResponsiva from "../shared/imagem-responsiva/ImagemResponsiva";

export default {

  components:{
    "meu-painel":Painel,
    "imagem":ImagemResponsiva
  },

  data(){
    return{
      fotos:[],
      filtro:""
    }
  },
  computed:{//metodo
    fotosComFiltro(){
      if(this.filtro){
        //filtrar
        let exp = new RegExp(this.filtro.trim(),"i")
        return this.fotos.filter(foto => exp.test(foto.titulo))
      }else{
        return this.fotos
      }
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

  .borda-cor-especial{
    border-color: darkred;
  }

  .filtro{
    display: block;
    width: 50%;
    margin: auto;
  }
</style>
