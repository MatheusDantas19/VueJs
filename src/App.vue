<template>
  <div>
    <meu-menu></meu-menu>
    <main class="corpo">
      <!--Hora tem que exibir um componente, hora outro-->
      <transition name="pagina"></transition>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
import Menu from "./components/menu/Menu";

export default {
  components:{
    "meu-menu":Menu
  },
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
