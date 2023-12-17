<template>
  <base-container title="Vuex"> 
  <favorite-value-vue></favorite-value-vue>
  <change-counter-vue></change-counter-vue>
  <button @click="addOne">Add 10</button>
  <the-counter></the-counter>
</base-container>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import ChangeCounterVue from './components/ChangeCounter.vue';
import FavoriteValueVue from './components/FavoriteValue.vue';
import TheCounter from './components/TheCounter.vue';

export default {
  components: {
    BaseContainer,
    TheCounter,
    ChangeCounterVue,
    FavoriteValueVue,
  },
  methods: {
    addOne() {
      // this.$store.commit('increase',{value:10})
      this.$store.commit({
        type: 'increase',
        value: 10,
      });
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
