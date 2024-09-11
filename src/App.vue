<template>
  <div id="app">
    <Navbar @search="updateSearch" />
    <PlayersList :players="filteredPlayers" />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import PlayersList from './components/PlayersList.vue';
import playersData from './data/players.json';

export default {
  data() {
    return {
      search: '',
      players: playersData.originalPlayers,
    };
  },
  computed: {
    filteredPlayers() {
      return this.players.filter(player => {
        const searchTerm = this.search.toLowerCase();
        return player.name.toLowerCase().includes(searchTerm) || 
               player.team_name.toLowerCase().includes(searchTerm);
      });
    },
  },
  methods: {
    updateSearch(term) {
      this.search = term; 
    },
  },
  components: {
    Navbar,
    PlayersList,
  },
};
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
</style>
