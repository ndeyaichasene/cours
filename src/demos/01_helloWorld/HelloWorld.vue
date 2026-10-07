<script setup>
const message= "Breukhhhhh";
</script>


<template>

<section class="card">
    
<h1>01_Hello word</h1>
<p>Premier composant vue (SFC)</p>
<div class="box"> 
<strong>message:</strong> {{ message.toUpperCase()}}
</div>

</section>


</template>


<style scoped>
.card {
    padding: 16px;
    border: 1px;
    border-radius: 12px;
}
.box{
    margin-top: 10px;
    padding: 10px;
    border: 1px dashed #ccc;
    border-radius: 12px;

}
</style>