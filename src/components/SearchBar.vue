<template>
  <div class="search-bar">
    <input
      type="text"
      placeholder="Search songs..."
      v-model="searchQuery"
      @input="onSearchInput"
    />
  </div>
</template>

<script>
import { ref } from 'vue'; // Import ref

export default {
  name: 'SearchBar',
  props: ['onSearch'],
  setup(props) {
    const searchQuery = ref(''); // Create a reactive variable for the input

    const onSearchInput = () => {
      props.onSearch(searchQuery.value); // Pass the input value to the parent component
    };

    return { searchQuery, onSearchInput };
  },
};
</script>

<style scoped>
.search-bar {
  margin-bottom: 20px;
}
input {
  width: 100%;
  padding: 10px;
  font-size: 1em;
}
</style>
