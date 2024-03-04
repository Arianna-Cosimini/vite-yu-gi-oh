<script>
import axios from 'axios';
import AppNav from './components/AppNav.vue';
import CardsList from './components/CardsList.vue';

import { store } from './store.js';


export default {

  components: {
    CardsList,
    AppNav,
  },


  data() {
    return {
      cards: [],
      currentPage: 1,
      resultsPerPage: 50,
    }
  },

  created() {
    this.fetchCards();
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
          this.cards = res.data.data;
        })
    },
  },
}

</script>

<template>
  <AppNav></AppNav>
  <CardsList :cards="cards"></CardsList>

</template>

<style></style>