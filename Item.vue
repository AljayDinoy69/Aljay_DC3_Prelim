<template>
  <div class="item">
    <div v-if="isVisible">
      <h3>{{ item.name }}</h3>
      <p>Price: {{ item.price }}</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
  </div>
  </template>
  
  <script>
  export default {
    name: 'Item',
    props: {
      item: Object
    },
    computed: {
      isVisible() {
        return this.item.isVisible;
      }
    },
    methods: {
      addToCart() {
        this.$emit('add-to-cart', this.item);
      }
    }
  }
  </script>
  
  <style scoped>
  .item {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 8px;
    background-color: #fff;
    text-align: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .item h3 {
    font-size: 18px;
    margin-bottom: 10px;
  }
  
  .item p {
    font-size: 16px;
    margin-bottom: 20px;
  }
  
  .item button {
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    background-color: #007bff;
    color: #fff;
    cursor: pointer;
    font-size: 16px;
  }
  
  .item button:hover {
    background-color: #0056b3;
  }
  </style>