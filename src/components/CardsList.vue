<script>
// STATE MANAGEMENT 
import { store } from '../store';
// IMPORT COMPONENTS 
import Card from './Card.vue'
export default {
    components: {
        Card
    },
    data() {
        return {
            store
        }
    },
}
</script>
<template lang="">
    <div class="container">
        <div class="row">
            <!-- CARD COUNTER  -->
            <div class="bg_black">
                Found {{ store.cards.length }} cards
            </div>
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


        .bg_black {
            width: 100%;
            background-color: #000;
            color: $white;
            padding: 10px;
            font-weight: 600;
        }
    }
}
</style>