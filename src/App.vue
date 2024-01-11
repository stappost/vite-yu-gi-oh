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
  methods: {
    // TAKE ARRAY IN API 
    getCards() {


      axios.get(store.endpoint).then(results => {
        store.cards = results.data.data
        store.loading = false
      })
    },
    getArch() {
      axios.get(store.archApiUrl).then(results => {
        store.arch_array = results.data
        console.log(store.arch_array)
      })
    }


  },
  created() {
    this.getCards();
    this.getArch()
  }

} 
</script>
<template lang="">
  <Loader v-if="store.loading"/>
  <div v-else>
    <AppHeader />
    <AppSearch :arch_array="store.arch_array"/>
    <CardList />
  </div>
</template>
<style lang="scss">
@use './styles/generals.scss'
</style>