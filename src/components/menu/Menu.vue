<template>
    <header class="mb-5 p-3">
        <nav class="navbar navbar-expand-lg navbar-light bg-light fixed-top">
            <router-link to="/" class="navbar-brand" id="titulo-nav">Vue Js - FrontEnd</router-link>
            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
            <b-collapse id="nav-collapse" is-nav>
              <ul class="navbar-nav">
                <li v-for="rota in rotas">
                    <router-link :to="rota.path ? rota.path : '/'" 
                    class="nav-item nav-link">{{rota.titulo}}</router-link>
                </li>
              </ul>
            </b-collapse>        
        </nav>
    </header>
</template>

<script>
export default {
    props:["rotas"],
    isActive: function(path){
        if(this.$route.path == path){
            return true;
        }
    }
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css?family=Pacifico&display=swap');
    #titulo-nav{
        font-family: 'Pacifico', cursive; 
        color:darkred;
        font-weight: 900;
        font-size: 1.2em;
    }
</style>