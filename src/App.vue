<template>
  <div id="app">
    <Header title="Portafolio GH" />

    <Container />
    <Footer />
    
  </div>
</template>

<script>
  import Header from "./components/Header";
  import Footer from "./components/Footer";
  import Container from "./components/Container";

  //importando el Header creado con su propiedades
  //
  export default {
    components: {
      Header,
      Footer,
      Container,
      
    },
  };
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Yusei+Magic&display=swap');

  * {
    margin: 0;
    padding: 0;
    font-family: 'Yusei Magic', sans-serif;
  }
</style>