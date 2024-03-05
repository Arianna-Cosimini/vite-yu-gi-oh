<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store,
        }
    },

    name: 'CardsList',


}

</script>

<template>

    <div class="container-big">

        <div class="container-small">
            <div class="found-cards">
                <span>
                    Founds {{ store.cards.length }} Cards
                </span>
            </div>
    
            <div class="cards">
                <div v-for="currentCard in store.cards" class="card">
                    <div class="img-card">
                        <img :src="currentCard.card_images[0].image_url" alt="">
    
                    </div>
                    <div class="text-card">
                        <div class="text-name">
                            <span class="name">{{ currentCard.name }}</span>
                            
                        </div>
                        
                        <div class="text-archetype">
                            <span class="archetipe">{{ currentCard.archetype }}</span>
    
                        </div>

                    </div>
                </div>
    
            </div>

        </div>

    </div>


</template>

<style lang="scss">
.container-big {
    max-width: 1200px;
    margin: 0 auto;
    background-color: #fff;
    color: black;

    padding: 50px 0;

    .found-cards {
        background-color: #212529;
        padding: 20px 10px;
        color: #fff;
    }
}

.container-small{
    max-width:1100px;
    margin: 0 auto;
}

.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 25px;

    .card {
        width: calc(100% / 5 - 25px / 5 * 4);
        display: flex;
        gap: 20px;
        align-items: center;
        flex-direction: column;
        justify-content: space-between;

        background-color: #d48f38;

        padding-bottom: 20px;

        img {
            width: 100%;
        }

        .text-card{
            display: flex;
            flex-direction: column;
            align-items: center;
            
        }

        .text-name{
            text-align: center;
            display: flex;
            flex-direction: column;
        }

    }
}
</style>