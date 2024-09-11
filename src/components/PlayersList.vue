<template>
  <div>
    <h1>Players List</h1>
    <div class="player-list">
      <PlayerCard 
        v-for="player in players" 
        :key="player.name" 
        :player="player" 
      />
    </div>
  </div>
</template>

<script>
import PlayerCard from './PlayerCard.vue';

export default {
  name: 'PlayersList',
  props: {
    players: {
      type: Array,
      required: true,
    },
  },
  components: {
    PlayerCard,
  },
};
</script>

<style scoped>
.player-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

h1 {
  text-align: center;
  margin-bottom: 20px;
}
</style>
