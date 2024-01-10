<script>
import axios from "axios"
import AppHeader from './components/AppHeader.vue';
import { store } from './store';

export default {
  components: {
    AppHeader
  },
  data() {
    return {
      store
    }
  },
  methods: {
    getCards() {
      axios.get(store.endpoint).then(results => {
        store.cards = results.data.data
      })
    }
  },
  created() {
    this.getCards()
  }

} 
</script>
<template lang="">
  <div>
    <AppHeader />
  </div>
</template>
<style lang="scss">
@use './styles/generals.scss'
</style>