<template>
  <div id="app">
    <h1>Song List</h1>
    <SearchBar :onSearch="handleSearch" />
    <SongList :songs="filteredSongs" />
  </div>
</template>

<script>
import { ref, computed } from 'vue'; // Import ref and computed
import SearchBar from './components/SearchBar.vue';
import SongList from './components/SongList.vue';
import songsData from './data/songs.js';

export default {
  name: 'App',
  components: { SearchBar, SongList },
  setup() {
    const songs = ref(songsData); // Create a reactive variable for songs
    const searchQuery = ref(''); // Create a reactive variable for the search query
    
    const handleSearch = (query) => {
      searchQuery.value = query.toLowerCase();
    };

    const filteredSongs = computed(() => { // Use computed to filter songs dynamically
      return songs.value.filter(song =>
        song.TITLE.toLowerCase().includes(searchQuery.value)
      );
    });

    return { filteredSongs, handleSearch };
  },
};
</script>

<style scoped>
#app {
  font-family: Arial, sans-serif;
  padding: 20px;
}
</style>
