<script>

export default {

    name: 'CardsList',


    props: {
        cards: Array,
    }


}

</script>

<template>

    <div class="container">

        <div class="found-cards">
            <span>
               Founds {{ cards.length }} Cards
            </span>
        </div>

        <div v-for="currentCard in cards" class="cards">
            {{ currentCard.name }}
        </div>

    </div>


</template>

<style lang="scss">
.container {
    max-width: 1200px;
    margin: 0 auto;
    background-color: #fff;
    color: black;

    .found-cards{
        background-color: #212529;
        padding: 20px 10px;
        color: #fff;
    }
}
</style>