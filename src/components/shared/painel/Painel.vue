<template>
    <div class="card borda-cor-especial" style="width: 18rem;">
        <div class="card-header bg-info">
            <h5 class="text-center">{{ titulo }}</h5>
        </div>
        <slot></slot>
        <div class="card-body">
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        </div>
    </div>   
</template>

<script>
export default {
  props: ["titulo"]
}

</script>

<style scoped>

  .borda-cor-especial{
    border-color: darkred;
  }


</style>
