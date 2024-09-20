<template>
    <div>
      <h2>Add a New Recipe</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="name">Recipe Name:</label>
          <input type="text" v-model="name" required />
        </div>
        <div>
          <label for="ingredients">Ingredients:</label>
          <div v-for="(ingredient, index) in ingredients" :key="index">
            <input type="text" v-model="ingredient.name" placeholder="Ingredient" required />
            <p>Quantity:</p>
            <input type="number" v-model="ingredient.quantity" placeholder="Quantity" required />
            <p>Cost:</p>
            <input type="number" v-model="ingredient.cost" placeholder="Cost" required />
            <p>Calories:</p>
            <input type="number" v-model="ingredient.calories" placeholder="Calories" required />
          </div>
          <button type="button" @click="addIngredient">Add Ingredient</button>
        </div>
        <button type="submit">Add Recipe</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: '',
        ingredients: [{ name: '', quantity: 0, cost: 0, calories: 0 }]
      };
    },
    methods: {
      addIngredient() {
        this.ingredients.push({ name: '', quantity: 0, cost: 0, calories: 0 });
      },
      submitForm() {
        const newRecipe = {
          name: this.name,
          ingredients: this.ingredients
        };
        this.$emit('add-recipe', newRecipe);
        this.name = '';
        this.ingredients = [{ name: '', quantity: 0, cost: 0, calories: 0 }];
      }
    }
  };
  </script>
  
  