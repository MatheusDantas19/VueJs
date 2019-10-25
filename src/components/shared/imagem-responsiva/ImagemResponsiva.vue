<template>
    <img class="card-img-top" :src="url" :alt="titulo">
</template>

<script>
export default {
    props:["url","titulo"]
}
</script>
