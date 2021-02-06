<template>
    <header>
        <h1>{{title}}</h1>

    </header>

</template>

<script>
    export default  {
     props:{
         title: String,
     },
    };
</script>

<style scoped>
    h1 {
        background: #1d1c1f;
        color: #b7a4c9;
        padding: 1rem;
        text-align: center;
    }
</style>