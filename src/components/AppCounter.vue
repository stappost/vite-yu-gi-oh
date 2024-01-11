<script>
export default {
    computed: {
        countercard() {
            return this.cards.length
        }
    },
    props: {
        cards: Array
    }
}
</script>
<template lang="">
    <div class="bg_black">
        Found {{ countercard }} cards
    </div>
</template>
<style lang="scss" scoped>
.bg_black {
    width: 100%;
    background-color: #000;
    color: #fff;
    padding: 10px;
    font-weight: 600;
}
</style>