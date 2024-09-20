<template>
  <div id="app">
    <h1>Recipe Cost and Calorie Tracker</h1>
    <RecipeForm @add-recipe="addRecipe" />
    <RecipeList :recipes="recipes" />
  </div>
</template>

<script>
import RecipeForm from './components/RecipeForm.vue';
import RecipeList from './components/RecipeList.vue';

export default {
  name: 'App',
  components: {
    RecipeForm,
    RecipeList
  },
  data() {
    return {
      recipes: []
    };
  },
  methods: {
    addRecipe(recipe) {
      this.recipes.push(recipe);
    }
  }
};
</script>
