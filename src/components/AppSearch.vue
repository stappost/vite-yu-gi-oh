<script>

import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    },
}
</script>
<template lang="">
    <div class="container">
        <select v-model="store.filter" @change="$emit('getFilter')">
            <option value="">filtra</option>
            <option v-for="arch, index in store.arch_array" :value=arch.archetype_name>{{arch.archetype_name}}</option>
        </select>
    </div>
</template>
<style lang="scss" scoped>
.container {
    margin-top: 20px;

    select {
        min-width: 200px;
        padding: 5px 0;
        border-radius: 5px;
        border: 0px;
        margin: 20px auto;
    }
}
</style>