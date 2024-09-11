<template>
    <div class="player-card">
      <img :src="player.image" alt="Player Image" class="player-image" />
      <div class="card-body">
        <h5 class="card-title">{{ player.name }}</h5>
        <p class="card-text">Matches: {{ player.matches }}</p>
        <p class="card-text">Runs: {{ player.runs }}</p>
        <p class="card-text">50s/100s: {{ player["50s"] }}/{{ player["100s"] }}</p>
        <p class="card-text">Highest Score: {{ player.highest_score }}</p>
        <p class="card-text">Team Name: {{ player.team_name }}</p>
        <p class="card-text">Best Bowling Figures: {{ player.best_bowling_figures }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "PlayerCard",
    props: {
      player: Object,
    },
  };
  </script>
  
  <style scoped>
  .player-card {
    max-width: 250px;
    border: 1px solid #ddd;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
    margin: 10px;
  }
  
  .player-card:hover {
    transform: scale(1.05);
  }
  
  .player-image {
    width: 100%;
    height: auto;
  }
  
  .card-body {
    padding: 10px;
    text-align: center;
  }
  
  .card-title {
    font-size: 1.25rem;
    font-weight: bold;
  }
  
  .card-text {
    font-size: 0.9rem;
    margin-bottom: 5px;
  }
  </style>
  