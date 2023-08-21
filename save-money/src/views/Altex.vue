<template>
  <div class="test">
    <h1>This is a test page</h1>
    <products-list :products="products" />
  </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';
import VueAxios from 'vue-axios';
import endpointArray from '@/constants/endpoints';
import ProductsList from '@/components/ProductsList.vue';

Vue.use(VueAxios, axios);

export default Vue.extend({
  name: 'TestList',
  components: {
    'products-list': ProductsList,
  },
  data() {
    return {
      products: [],
    };
  },
  created() {
    this.startDataFetching();
  },
  methods: {
    async startDataFetching() {
      await this.getData();
      setInterval(this.getData, 10000);
    },
    async getData() {
      console.log('get data is called');
      const resp = await Vue.axios.get(endpointArray);
      this.products = resp.data.entries.slice(0, 5);
      console.log(resp.data.entries);
    },
  },
});
</script>
