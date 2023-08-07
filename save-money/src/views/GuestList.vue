<template>
  <div>
    <button @click="toggleVisibility('guestListVisibility')">
      {{ guestListVisibility ? 'Hide' : 'Show' }} guest list
    </button>
    <ul v-if="guestListVisibility || true">
      <li v-for="(guest, index) in guestListData" :key="index">
        Name: {{ guest.name }}
        <div>
          <button @click="guestListData[index].isOpen = !guest.isOpen" class="details-button">
            {{ detailsVisibility ? 'Hide' : 'Show' }} Details
          </button>
          <ul v-if="guest.isOpen">
            <li><strong>Acces type:</strong></li>
            <li><strong>Plus One:</strong></li>
          </ul>
        </div>
      </li>
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
  data() {
    return {
      guestListData: [{ name: 'John', isOpen: false }, { name: 'Jane', isOpen: false }, { name: 'Mark', isOpen: false }],
      guestListVisibility: false,
      detailsVisibility: false,
    };
  },
  methods: {
    toggleVisibility(property: string) {
      // this[property] = !this[property];
    },
  },
});
</script>

<style scoped>
.details-button {
  margin: 0.2rem;
  padding: 0.2rem;
  background-color: #8842b8;
  border-radius: 8px;
  font-size: small;
}
</style>
