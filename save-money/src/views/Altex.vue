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
      endpointArray.forEach(async (item) => {
        setInterval(async () => {
          console.log('get data is called');
          const { data } = await Vue.axios.get(item);
          this.products = data.entries.slice(0, 5);
          console.log(this.products);
        }, 10000);
      });
    },
  },
});
</script>
