<template>
    <div>
      <h2>Recipe List</h2>
      <div v-for="(recipe, index) in recipes" :key="index">
        <RecipeItem :recipe="recipe" />
      </div>
    </div>
  </template>
  
  <script>
  import RecipeItem from './RecipeItem.vue';
  
  export default {
    props: ['recipes'],
    components: {
      RecipeItem
    }
  };
  </script>
  