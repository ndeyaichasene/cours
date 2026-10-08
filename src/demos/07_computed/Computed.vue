<script setup>
import { computed,reactive } from 'vue';

const produits = reactive([
    { nom: 'Banane', prix: 200, quantite: 3 },
    { nom: 'Orange', prix: 500, quantite: 2 },
    { nom: 'Mangue', prix: 750, quantite: 3 }
]);

const total = computed(() => {
    return produits.reduce((somme, produit) => somme + produit.prix * produit.quantite, 0);
});
</script>

<template>
  <section class="card">
    <h2>07 - computed()</h2>

    <ul>
      <li v-for="produit in produits" :key="produit.nom">
       {{ produit.nom }} : {{ produit.prix }} × {{ produit.quantite }} -> {{ produit.prix * produit.quantite }} FCFA
      </li>
    </ul>

    <h3>Total : {{total}} FCFA</h3>

    <p class="note">
      Le total se met à jour automatiquement.
    </p>
  </section>
</template>

<style scoped>
.card { padding:16px; border:1px solid #eee; border-radius:12px; }
.note { margin-top:8px; color:#555; }
</style>