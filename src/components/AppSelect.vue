<script>
import { store } from '../store.js';


export default {

    props: {
        archetypes: Array,

    },

    data() {
        return {
            store,
        }
    },

    name: 'AppSelect',


}

</script>

<template>
    <nav>
        <div class="text-nav">
            <h1>Yu-Gi-Oh Api</h1>

            <select v-model="store.selectText" @change="$emit('search')" class="form-select w-25"
                aria-label="Default select example">

                <option v-for="currentArchetype in archetypes" :value="currentArchetype.archetype_name">{{
                currentArchetype.archetype_name }}</option>
            </select>
        </div>
    </nav>

</template>

<style lang="scss">
nav {
    background-color: #fff;
    color: black;

    padding: 10px;
}

.text-nav {
    display: flex;
    justify-content: space-between;
}
</style>