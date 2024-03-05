<script>
import axios from 'axios';
import AppNav from './components/AppNav.vue';
import AppSelect from './components/AppSelect.vue';
import CardsList from './components/CardsList.vue';

import { store } from './store.js';


export default {

  components: {
    CardsList,
    AppNav,
    AppSelect,
  },


  data() {
    return {
      // cards: [],
      currentPage: 1,
      resultsPerPage: 50,
      store,
      archetypes: [],

    }
  },

  created() {
    this.fetchCards();
    this.searchArchetype();
  },

  mounted() {

  },


  methods: {

    fetchCards() {
      const offset = (this.currentPage - 1) * this.resultsPerPage;
      axios
        .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=${this.resultsPerPage}&offset=${offset}`)
        .then(res => {
          console.log(res.data.data);
          this.store.cards = res.data.data;
        })
    },

    searchArchetype() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(res => {
          this.archetypes = res.data; 
        })
        .catch(error => {
          console.error('Si è verificato un errore durante la ricerca degli archetipi:', error);
        });
    }
  },
}

</script>

<template>
  <AppNav></AppNav>
  <AppSelect :archetypes="archetypes"></AppSelect>
  <CardsList :cards="cards"></CardsList>

</template>

<style></style>