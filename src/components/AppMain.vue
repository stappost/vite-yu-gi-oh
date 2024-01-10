<script>
import AppSearch from './AppSearch.vue';
import CardList from './CardsList.vue'
export default {
    components: {
        AppSearch,
        CardList
    }
}
</script>
<template lang="">
    <div class="bg_yellow">
        <div class="container">
            <AppSearch />
            <CardList />
        </div>
    </div>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.bg_yellow {
    background-color: $dark_yellow;
    padding: 20px 0;
}
</style>