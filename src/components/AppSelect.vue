<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store,
        }
    },

    name: 'AppSelect',


}

</script>

<template>


    <select class="form-select w-25" aria-label="Default select example">
        
        <option v-for="currentArchetype in store.cards" value="1">{{ currentArchetype.archetype }}</option>
    </select>
</template>

<style lang="scss"></style>