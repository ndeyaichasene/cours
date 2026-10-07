<script setup>
const image = "https://i.pinimg.com/736x/60/f0/6a/60f06a845a62e732910565b20c4a0e45.jpg";
const btn = true;
</script>


<template>

    <section class="card">
        <img :src="image" alt="">
        <button :disabled="1>2">Click</button>
    </section>

</template>


<style scoped>

</style>