<script setup>
import { ref } from 'vue';

const step=ref(1);
const count = ref(0);
function increment(){
    count.value +=step.value;
}
function reset(){
    count.value = 0;
}
</script>


<template>

    <section class="card">
        <div>
            <button @click="increment">Increment</button>
            <button @click.right.prevent="reset">Reset</button>
        </div>
        <div>
            <input type="number" min="1" v-model="step" @keyup.enter="increment">
        </div>
        <h4>{{ count }}</h4>
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