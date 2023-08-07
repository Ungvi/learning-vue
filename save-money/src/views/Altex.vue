<template>
  <div class="test">
    <h1>This is an test page</h1>
    <products-list :products="products" />
  </div>
</template>

<script>
import Vue from 'vue';
import ProductsList from '@/components/ProductsList.vue';

export default Vue.extend({
  name: 'TestList',
  components: {
    'products-list': ProductsList,
  },
  data: () => ({
    products: [],
  }),
  created() {
    this.getData();
  },
  methods: {
    // TODO METHODS
    getData() {
      // api call to the server which retireves data
      console.log('get data is called');
      // save it to the data
      this.products = [
        { name: 'PC', id: 1, price: 10 },
        { name: 'PC', id: 2, price: 10 },
        { name: 'PC', id: 3, price: 10 },
        // { name: 'PC', id: 4, price: 10 },
        // { name: 'PC', id: 5, price: 10 },
        // { name: 'PC', id: 6, price: 10 },
        // { name: 'PC', id: 7, price: 10 },
        // { name: 'PC', id: 8, price: 10 },
      ];
    },
  },
});
</script>
