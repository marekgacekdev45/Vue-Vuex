<template>
  <button @click="inc">Add 2</button>
  <button @click="increase({value:12})">Add 12</button>
</template>

<script>
import { mapActions } from 'vuex';
export default {
  methods: {
    // addOne() {
    //   this.$store.dispatch('increment')
    // },
    // ...mapActions(['increment','increase'])
    ...mapActions('counter',{
      inc:'increment',
      increase:'increase'

    })
  },
  
};
</script>
