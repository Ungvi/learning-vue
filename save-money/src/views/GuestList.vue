<template>
    <div class="guest">
      <ul>
        <li v-for="(guest, index) in guests" :key="index">{{ guest }}</li>
      </ul>
    </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'GuestList',
  props: {
    guests: {
      type: Array,
      default: () => [],
    },
  },
});
</script>

<!-- Assignment done -->