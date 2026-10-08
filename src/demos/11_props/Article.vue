<script setup>
import { defineProps } from 'vue';
//1er methode pour définir les props
//  defineProps({
//     product:  Object,
//     quantite : Number
// }); 

//2eme methode pour définir les props
// const props = defineProps({
//     product: Object,
//     quantite: Number
// });
// console.log(props.product);

//3eme methode pour définir les props
const props = defineProps({
    product:{
        type: Object,
        required: true,
        validator: (value) => typeof value.name === 'string'
    },
    quantite: {
        type: Number,
        default: 0,
        validator: (value) => value >= 0
    }
});

</script>

<template>
      <article class="card" >
        <h3 class="name">{{ product.name }}</h3>
        <p class="price">{{ product.price.toLocaleString() }} FCFA</p>
        <p class="meta">ID: {{ product.id }}</p>
        <p class="meta">Quantité: {{ quantite }}</p>
      </article>
</template>

<style scoped>
.card { padding: 14px; border: 1px solid #eee; border-radius: 12px; background: #fff; }
.name { margin: 0; font-size: 16px; }
.price { margin: 6px 0 0; font-weight: 700; }
.meta { margin: 6px 0 0; color: #666; font-size: 12px; }
</style>