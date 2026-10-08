<script setup>
import { ref } from 'vue';

const products = ref([
    {id: 1, nom: 'Banane', prix: 200, quantite: 3 },
    {id: 2, nom: 'Orange', prix: 500, quantite: 2 },
    {id: 3, nom: 'Mangue', prix: 750, quantite: 3 }
]);

const removeProduct = (id) => {
    products.value = products.value.filter(p => p.id !== id);
}
</script>

<template>
  <section class="card">
    <h2>09 - Lists</h2>

    <ul>
      <li v-for="p in products" :key="p.id">
        {{p.nom}} - {{p.prix}} FCFA
        <button @click="removeProduct(p.id)">❌</button>
      </li>
    </ul>
  </section>
</template>

<style scoped>
.card { padding:16px; border:1px solid #eee; border-radius:12px; }
li { display:flex; justify-content:space-between; width:250px; }
button { border:none; background:none; cursor:pointer; }
</style>