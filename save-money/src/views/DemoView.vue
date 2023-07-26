<template>
  <div>
    <div class="demo">
      <h1>First Name: {{ firstName }}</h1>
      <button @click="toggleVisibility('greetingVisibility')">
        {{ greetingVisibility ? 'Hide' : 'Show' }} greeting</button>
      <p v-if="greetingVisibility">{{ greeting }}</p>
      <section>
        <div>
        <button @click="toggleVisibility('groceryListVisibility')">
          {{ groceryListVisibility ? 'Hide' : 'Show' }} grocery list
        </button>
        <ul v-if="groceryListVisibility">
          <li v-for="(grocery, index) in groceryList" :key="index">
            {{ grocery }}
          </li>
        </ul>
        </div>
        <div>
          <button @click="toggleVisibility('guestListVisibility')">
            {{ guestListVisibility ? 'Hide' : 'Show' }} guest list
          </button>
              <guest-list v-if="guestListVisibility" :guests="guestListData"></guest-list>
          </div>
      </section>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import GuestList from './GuestList.vue';

export default Vue.extend({
  name: 'DemoView',
  components: {
    GuestList,
  },
  // state
  data: () => ({
    firstName: 'Ervin',
    greetingVisibility: false,
    groceryList: ['Carrots', 'Oats', 'Apples', 'Eggs'],
    groceryListVisibility: false,
    guestListData: ['John', 'Jane', 'Mark'],
    guestListVisibility: false,
  }),
  // computed
  computed: {
    greeting() {
      return `Welcome to the website ${this.firstName}!`;
    },
  },
  // methods
  methods: {
    toggleVisibility(this: any, property: string) {
      this[property] = !this[property];
    },
  },
});
</script>

<style>
button {
  margin: 0.5rem;
  padding: 0.5rem;
  background-color: #42b883;
  border-radius: 8px;
  font-size: medium;
  font-weight: bold;
}
</style>
