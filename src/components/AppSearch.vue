<script>
export default {
    props: {
        arch_array: Array
    }
}
</script>
<template lang="">
    <div class="container">
        <select >
            <option value="">filtra</option>
            <option v-for="arch, index in arch_array">{{arch.archetype_name}}</option>
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