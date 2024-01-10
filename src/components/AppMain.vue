<script>
import AppSearch from './AppSearch.vue';

export default {
    components: {
        AppSearch
    }
}
</script>
<template lang="">
    <div class="bg_yellow">
        <div class="container">
            <AppSearch />

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