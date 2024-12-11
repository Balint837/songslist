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
import { ref } from 'vue';

export default {
  name: 'SearchBar',
  props: ['onSearch'],
  setup(props) {
    const searchQuery = ref('');

    const onSearchInput = () => {
      props.onSearch(searchQuery.value);
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
