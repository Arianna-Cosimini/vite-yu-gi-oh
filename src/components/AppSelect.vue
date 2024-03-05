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


    <select class="form-select w-25" aria-label="Default select example">

        <option v-for="currentArchetype in archetypes" value="1">{{ currentArchetype.archetype_name }}</option>
    </select>
</template>

<style lang="scss"></style>