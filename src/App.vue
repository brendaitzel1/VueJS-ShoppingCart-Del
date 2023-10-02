<script setup>
import { ref } from 'vue';
const header = ref('App Lista de compras');
const items = ref([
  {id: 1, label: '10 bolillos 🥖'},
  {id: 2, label: '1 lata de frijoles🫘'},
  {id: 3, label: '2 lata de atún 🐟'}
]);
const newItem = ref('');
const newItemHighPriority = ref(false);
</script>

<template>
  <h1> <i class="material-icons shopping-cart-icon">local_mall</i> {{ header }}</h1>
  <input v-model.trim= "newItem" type="text" placeholder="Ingresar nuevo Articulo ">

  <!--check boxes -->
  <label>
    <input v-model="newItemHighPriority" type="checkbox">
    Alta Prioridad
  </label>

  {{ newItemHighPriority ? "🔥" : "🧊" }}

  <ul>
    <li v-for="{ id, label } in items" v-bind:key="id">
      🔹 {{ label }}
    </li>
  </ul>
</template>

<style scoped>
.shopping-cart-icon{
  font-size: 2rem;

}

</style>
