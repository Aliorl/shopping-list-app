<template>
  <div class="container">
  <div id="app">
    <h1>Shopping List App</h1>
    <shoppingListApp msg="Welcome to Shopping List App" />
  </div>
</div>
</template>

<script>
import shoppingList from './components/shoppingListApp.vue'

export default {
  name: 'app',
  components: {
    shoppingListApp: shoppingList
  }
}
</script>

<style>
@import '/src/assets/style.css';
</style>