<template>
  <div class="product-item">
    <h5>Name: {{ product.API }}</h5>
    <h6>Category: {{ product.Category }}</h6>
    <h6>HTTPS: {{ product.HTTPS }}</h6>
  </div>
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
  name: 'ListItem',
  props: {
    product: {
      required: true,
    },
  },
});
</script>

<style>
.product-item {
  border: 1px solid red;
  padding: 25px;
  margin: 15px;
  width: 100px;
}
</style>
