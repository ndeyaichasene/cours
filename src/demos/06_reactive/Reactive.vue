<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';
const info = reactive({ nom: "Aicha Sene", tel: "775448107", solde: 2500000 });
const autreMontant = ref(0);
const cpt = ref(0);

function incrementer(montant) {
  if (cpt.value < 10) {
    info.solde += montant;
    cpt.value++;
  } 
  autreMontant.value = 0;
  return cpt.value;
}
</script>

<template>
  <section class="card">
    <h2>09 - reactive()</h2>

    <div class="box">
      <p><strong>Nom :</strong> {{ info.nom }}</p>
      <p><strong>Téléphone :</strong> {{ info.tel }}</p>
      <p><strong>Solde :</strong> {{info.solde}} FCFA</p>
      <p><strong>Nombre d'ajouts :</strong> {{ cpt}}/10</p>
    </div>

    <div class="actions" >
      <button @click="incrementer(5000)">+5 000</button>
      <button @click="incrementer(10000)">+10 000</button>
      <input type="number" v-model.number="autreMontant" placeholder="Modifier le solde" @keyup.enter="incrementer(autreMontant)" />
    </div>

    <p class="note">
      <code>reactive()</code> est idéal pour les objets complexes.
    </p>
  </section>
</template>

<style scoped>
.card { padding:16px; border:1px solid #eee; border-radius:12px; }
.box { padding:12px; background:#fafafa; border-radius:10px; }
.actions { display:flex; gap:10px; margin-top:10px; }
button { padding:8px 10px; border:1px solid #ddd; border-radius:8px; }
.note { margin-top:8px; color:#555; }
</style>