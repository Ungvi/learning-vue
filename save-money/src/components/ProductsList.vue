<template>
  <div class="products-container">
    <product-item
      v-for="product in products"
      :key="product.id"
      :product="product"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import ProductItem from './ProductItem.vue';

export default Vue.extend({
  name: 'ListComponent',
  components: {
    ProductItem,
  },
  props: {
    products: {
      required: true,
    },
  },
});
</script>

<style>
.products-container {
  display: flex;
  flex-direction: row;
}
</style>
