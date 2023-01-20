<template>
  <div id="app">
    <add-products></add-products>
    <view-products></view-products>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import ViewProducts from "./components/ViewProducts.vue";
import AddProducts from "./components/AddProducts.vue";

export default {
  name: "App",
  components: {
    ViewProducts,
    AddProducts,
  },
};
</script>

<style>
*,
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: #2c3e50;
  padding-top: 30px;
}
#app {
  max-width: 700px;
  margin: 0 auto;
}
</style>
