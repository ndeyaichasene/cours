<script setup>
const montant= 2500000;
const prime = 0.5;
const annee= new Date().getFullYear();
const person = {fullName: "Aicha Sene",role:"Fullstack"}
</script>


<template>

    <section class="card">
        <div class="div">Nom : {{ person.fullName }}</div>
        <div class="div">Role : {{ person.role }}</div>
        <div class="div">Montant : {{ montant.toLocaleString() }} FCFA</div>
        <div class="div">Annee : {{ annee }}</div>
        <div class="div">Salaire Net : {{ montant + montant * prime }}</div>
    </section>


</template>


<style scoped>
.card {
    padding: 16px;
    border: 1px;
    border-radius: 12px;
    border: 1px dashed #ccc;
}
.div{
    margin-top: 10px;
    padding: 10px;
    border-radius: 12px;

}
</style>