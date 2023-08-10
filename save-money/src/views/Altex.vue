<template>
  <div class="test">
    <h1>This is an test page</h1>
    <products-list :products="products" />
  </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';
import VueAxios from 'vue-axios';
import ProductsList from '@/components/ProductsList.vue';

Vue.use(VueAxios, axios);

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
      Vue.axios.get('https://api.publicapis.org/entries')
        .then((resp) => {
          this.products = resp.data.entries.slice(0, 5);
          console.log(resp.data.entries);
        });
    },
  },
});
</script>
