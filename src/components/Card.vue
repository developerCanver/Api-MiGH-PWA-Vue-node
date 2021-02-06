<template>

  <div  class="card">
      <h4> {{name}}</h4>
     
      <hr>
      <p> {{description}}</p>
     <hr>
          <p> <strong> {{author}}</strong></p>
         
          <button-url :url="url"/>
          <button-url 
          color="red" 
          :url="homepage" v-if="homepage != null"
          title="Deploy"
          />
  </div>

</template>

<script>
import ButtonUrl from './ButtonUrl.vue'
export default {
  components: { ButtonUrl },
    props:{
        name: String,
        description: String,
        author: String,
        url: String,
        homepage: String,
    }
}
</script>

<style scoped>

.card {
        width: 250px ;
        margin: 5px;
        border: solid 1px #eee;
        box-shadow: 1px 1px 4px #333;
        text-align: center;
        padding: 20px;

}
</style>