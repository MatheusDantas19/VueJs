<template>
  <div>
    <meu-menu :rotas="routes"></meu-menu>
    <main class="corpo">
      <!--Hora tem que exibir um componente, hora outro-->
      <transition name="pagina"></transition>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
import Menu from "./components/menu/Menu";
import {routes} from "./router"; 

export default {
  components:{
    "meu-menu":Menu
  },

  data(){
    return{
      routes:routes
    }
  }

}

</script>

<style>
  .corpo{
    font-family: Helvetica, sans-serif;
  }

  .pagina-enter, .pagina-leave-active{
    opacity: 0;
  }

  .pagina-enter-active, .pagina-leave-active{
    transition: opacity .4s;
  }
</style>
