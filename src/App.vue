<template>
  <div>
    <Navbar />
    <List />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
// import Json from './example_data.json'
import List from './pages/List.vue'
export default {
  components: {
    Navbar,
    List
  },
}
</script>

<style>
body, html {
  margin: 0;
  padding: 0;
}
</style>