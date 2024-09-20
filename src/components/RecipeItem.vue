<template>
    <div>
      <h3>{{ recipe.name }}</h3>
      <ul>
        <li v-for="(ingredient, index) in recipe.ingredients" :key="index">
          {{ ingredient.name }}: {{ ingredient.quantity }} units, ${{ ingredient.cost }}, {{ ingredient.calories }} calories
        </li>
      </ul>
      <p>Total Cost: ${{ totalCost }}</p>
      <p>Total Calories: {{ totalCalories }} kcal</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['recipe'],
    computed: {
      totalCost() {
        return this.recipe.ingredients.reduce((sum, ingredient) => sum + ingredient.cost, 0);
      },
      totalCalories() {
        return this.recipe.ingredients.reduce((sum, ingredient) => sum + ingredient.calories, 0);
      }
    }
  };
  </script>
  