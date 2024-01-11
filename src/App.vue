<script>
// IMPORT AXIOS 
import axios from "axios";

// IMPORT COMPONENTS 
import AppHeader from './components/AppHeader.vue';
import Loader from './components/Loader.vue';
import AppSearch from './components/AppSearch.vue';
import CardList from './components/CardsList.vue'
// STATE MANAGEMENT 
import { store } from './store';

export default {
  components: {
    AppHeader,
    Loader,
    AppSearch,
    CardList
  },
  data() {
    return {
      store
    }
  },
  created() {
    this.getCards();
    this.getArch()
  },
  methods: {
    // TAKE ARRAY IN API 
    getCards() {
      let apiCards = store.endpoint

      if (store.filter != '') {
        console.log(store.filter)
        apiCards += `&archetype=${store.filter}`
      }
      axios.get(apiCards).then(results => {
        store.cards = results.data.data
        store.loading = false
        store.filter = ''
      })
    },
    getArch() {
      axios.get(store.archApiUrl).then(results => {
        store.arch_array = results.data
      })
    }
  },



} 
</script>
<template lang="">
  <Loader v-if="store.loading"/>
  <div v-else>
    <AppHeader />
    <AppSearch @getFilter= "getCards"/>
    <CardList />
  </div>
</template>
<style lang="scss">
@use './styles/generals.scss'
</style>