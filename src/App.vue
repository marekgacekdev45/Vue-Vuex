<template>
  <base-container title="Vuex" v-if="isAuth">
    <favorite-value-vue></favorite-value-vue>
    <change-counter-vue></change-counter-vue>
    <button @click="addOne">Add 10</button>
    <the-counter></the-counter>
  </base-container>
  <base-container title="Auth">
    <user-auth></user-auth>
  </base-container>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import ChangeCounterVue from './components/ChangeCounter.vue';
import FavoriteValueVue from './components/FavoriteValue.vue';
import TheCounter from './components/TheCounter.vue';
import UserAuth from './components/UserAuth.vue';

export default {
  components: {
    BaseContainer,
    TheCounter,
    ChangeCounterVue,
    FavoriteValueVue,
    UserAuth,
  },
  methods: {
    addOne() {
      // this.$store.commit('increase',{value:10})
      this.$store.dispatch({
        type: 'counter/increase',
        value: 10,
      });
    },
  },
  computed: {
    isAuth() {
      return this.$store.getters.userIsAuth;
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
