<script>
export default {
    props: {
        single_card: Object
    }
}
</script>
<template lang="">
    <div class="card">
        <img :src="single_card.card_images[0].image_url" :alt="single_card.name">
        <h4>{{single_card.name}}</h4>
        <div class="archetype">{{single_card.archetype}}</div>
    </div>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.card {
    width: calc(100% / 5 - 20px);
    margin: 10px;
    background-color: $dark_yellow;
    text-align: center;
    object-fit: cover;

    img {
        width: 100%;
    }

    h4 {
        color: $white;
        margin: 10px 5px;
    }
}
</style>