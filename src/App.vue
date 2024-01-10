<script>
import axios from "axios"
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store';

export default {
  components: {
    AppHeader,
    AppMain
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
    <AppMain />
  </div>
</template>
<style lang="scss">
@use './styles/generals.scss'
</style>