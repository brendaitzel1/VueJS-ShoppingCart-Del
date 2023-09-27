<script setup>
 import { ref } from 'vue'
const header = ref('🛒 Shopping List App')
const items = ref([
  {id: 1, label: '10 bolillos 🥖'},
  {id: 2, label: '1 lata de frijoles 🫘'},
  {id: 3, label: '2 lata de atún 🐟'}
]);
</script>

<template>
<h1>{{ header }}</h1>
<ul>
  <li v-for="({ id, label }, index) in items" v-bind:key="id">
    🔹 - {{ index }} - {{ label }}
  </li>
</ul>
</template>


<style scoped>
.shopping-cart-icon{
  font-size: 2rem;

}

</style>
