<template>
    <div id="footer" >
        <footer>
            <h3 class="p-3">
            &copy; Carlos Ruiz - {{year}}

            </h3>
        </footer>
    </div>


</template>

<script>
    export default {
        computed: {
            year(){
                return new Date().getFullYear();
            }
        }
    };
</script>

<style scoped>
  h3 {
        background: #000;
        color: rgb(183, 164, 201);
        padding: 1rem;
        text-align: center;
       
    }

</style>