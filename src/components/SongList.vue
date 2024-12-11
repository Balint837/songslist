<template>
    <div class="song-list">
      <div v-for="song in songs" :key="song._id" class="song-item">
        <h3>{{ song.TITLE }}</h3>
        <p><strong>Genre:</strong> {{ song.GENRE }}</p>
        <p><strong>BPM:</strong> {{ song.BPM }}</p>
        <p><strong>Year:</strong> {{ song.YEAR }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'SongList',
    props: ['songs'],
  };
  </script>
  
  <style scoped>
  .song-list {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  }
  .song-item {
    border: 1px solid #ddd;
    padding: 10px;
    border-radius: 5px;
    width: calc(33.33% - 20px);
    box-sizing: border-box;
  }
  h3 {
    margin: 0 0 10px;
  }
  </style>
  