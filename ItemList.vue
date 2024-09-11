<template>
  <div class="item-list">
    <h2>Item-List</h2> 
      <div class="item-list-container">
        <Item
        v-for="item in filteredItems" 
      :key="item.id" 
      :item="item" 
      @add-to-cart="handleAddToCart"
    />
      </div>
  </div>
</template>

<script>
import Item from './Item.vue';

export default {
  name: 'ItemList',
  components: {
    Item
  },
  props: {
    products: Array
  },
  computed: {
    filteredItems() {
      return this.products.filter(item => item.isVisible);
    }
  },
  methods: {
    handleAddToCart(item) {
      console.log('Item added to cart:', item);
    }
  }
}
</script>

<style scoped>
 .item-list {
  padding: 20px;
  max-width: 1000px; /* Adjusted from 290% to a reasonable value */
  margin: 0 auto;
  background-color: aliceblue;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.item-list h2 {
  font-size: 20px;
  color: #333;
  margin-bottom: 20px;
  text-align: center;
}

.item-list-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>