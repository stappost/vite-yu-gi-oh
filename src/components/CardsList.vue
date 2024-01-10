<script>
import { store } from '../store';
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
            <Card v-for="card, index in store.cards" :key="index" :single_card="card"/>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.container {
    background-color: white;
    padding: 20px;
    margin: 20px 0;

    .row {
        display: flex;
        flex-wrap: wrap;
        margin: 0 auto;
    }
}
</style>