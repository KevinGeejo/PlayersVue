<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Sportz Interactive</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <form class="d-flex" @submit.prevent="onSearch">
            <input class="form-control me-2" type="search" placeholder="Search players or teams" v-model="searchTerm" />
            <button class="btn btn-outline-success" type="submit">Search</button>
          </form>
        </div>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    data() {
      return {
        searchTerm: '',
      };
    },
    methods: {
      onSearch() {
        this.$emit('search', this.searchTerm); 
      },
    },
  };
  </script>
  
  <style scoped>
 
  .navbar {
    margin-bottom: 20px;
  }
  </style>
  