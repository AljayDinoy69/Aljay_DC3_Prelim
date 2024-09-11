<template>
  <div id="app">
    <ItemList :products="products" />
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue';

export default {
  name: 'App',
  components: {
    ItemList
  },
  data() {
    return {
      products: [
        {  name: 'Product 1', price: 100, isVisible: true },
        {  name: 'Product 2', price: 200, isVisible: true },
        {  name: 'Product 3', price: 300, isVisible: true }
      ]
    }
  }
}
</script>

<style>
      #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: blue;
  margin-top: 60px;
  background-color: white;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>