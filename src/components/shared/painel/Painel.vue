<template>
  <div class="card borda-cor-especial card-largura col-12 col-md-4 p-0 m-4">
    <div class="card-header bg-info">
      <h5 class="text-center" @dblclick="visivel =! visivel">{{ titulo }}</h5>
    </div>

    <transition name="painel-fade">
      <div v-show="visivel">
        <slot></slot>
      </div>
    </transition>

    <div class="card-body">
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    </div>

  </div>   
</template>

<script>
export default {
  props: ["titulo"],
  data(){
    return{
      visivel:true
    }
  }
}

</script>

<style scoped>

  .borda-cor-especial{
    border-color: darkred;
  }
  .card-largura{
    max-width: 18rem;
  }

  .painel-fade-enter, .painel-fade-leave-active{
    opacity: 0;
  }

  .painel-fade-enter-active, .painel-fade-leave-active{
    transition: opacity .4s;
  }
  

</style>

<!--
painel-fade-enter // antes do elemento ser incluído ou removido, o estado atual
painel-fade-enter-active // quando o elemento esta sendo incluído
painel-fade-leave-active // quando o elemento esta sendo removido
-->