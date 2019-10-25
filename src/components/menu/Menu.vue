<template>
    <header class="mb-5 p-3">
        <nav class="navbar navbar-expand-lg navbar-light bg-light fixed-top">
            <router-link to="/" class="navbar-brand" >Vue</router-link>
            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
            <b-collapse id="nav-collapse" is-nav>
              <ul class="navbar-nav">
                <li><router-link to="/" class="nav-item nav-link">Home</router-link><span class="sr-only">(current)</span></li>
                <li><router-link to="/cadastro" class="nav-item nav-link">Cadastro</router-link></li>  

              </ul>
            </b-collapse>        
        </nav>
    </header>
</template>

<script>
export default {

}
</script>

<style scoped>
    branco{
        color:white!important;
    }
</style>