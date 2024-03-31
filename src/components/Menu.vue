<script setup>
import { reactive } from "vue"

const recipies = reactive([]);

function getData() {
  fetch('https://dummyjson.com/recipes')
    .then(res => res.json())
    .then(data => {
      data.recipes.forEach(single => {
        recipies.push(single)
      })
    })
    .catch(err => console.log(err))
}
getData()


// show alert with item name

function showAlert(itemName){
  alert(itemName)
}

</script>
<template>
  <h2>Menu Page</h2>
  <div class="p-1 bg-red-50">
    <div class="m-1 p-2 bg-green-200 rounded-sm" v-for="(singleRecipe, index) in recipies" :key="index">
      <p><span>{{ singleRecipe.id }}</span>. {{ singleRecipe.name }}</p>
      <div>
        <h2>Ingredients: </h2>
        <p class="m-1 inline-block bg-red-200 p-1 rounded" v-for="(ingre, index) in singleRecipe.ingredients"
          :key="index">{{ ingre }}</p>
      </div>
      <button @click="showAlert(singleRecipe.name)" class="p-2 bg-green-400 rounded">Order Now</button>
    </div>
  </div>
</template>
<style></style>
