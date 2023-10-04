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
  <div class="add-items form">

   <!-- Input de Nuevo Articulo -->
   <input v-on:keyup.enter="items.push({id: items.length + 1, label: newItem}) " v-model.trim="newItem" type="text" placeholder="Ingresar nuevo articulo">
  
    <!--check boxes -->
    <label>
      <input v-model="newItemHighPriority" type="checkbox">
      Alta Prioridad
    </label>
  
    {{ newItemHighPriority ? "🔥" : "🧊" }}
  
     <!--BOTTON DE UI -->
     <button v-on:click="items.push({id: items.length + 1, label: newItem})" class="btn btn-primary">Salvar Articulo </button>
  </div>

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
