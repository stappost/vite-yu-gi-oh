<script>
// STATE MANAGEMENT 
import { store } from '../store';
// IMPORT COMPONENTS 
import Card from './Card.vue';
import AppCounter from './AppCounter.vue'
export default {
    components: {
        Card,
        AppCounter
    },
    data() {
        return {
            store
        }
    },
    computed: {
        countercard() {
            return store.cards.length
        }
    }
}
</script>
<template lang="">
    <div class="container">
        <div class="row">
            <!-- CARD COUNTER  -->
            <AppCounter  :cards='store.cards'/>
            <!-- CREATION CARD LIST  -->
            <Card v-for="card, index in store.cards" :key="index" :single_card="card"/>
        </div>
    </div>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.container {
    background-color: white;
    padding: 20px;
    margin: 20px auto;

    .row {
        display: flex;
        flex-wrap: wrap;
        margin: 0 auto;

    }
}
</style>