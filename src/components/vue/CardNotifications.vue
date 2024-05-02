<script setup>
import {ref} from 'vue';
const counter = ref(0);

function decrement() {
    if(counter.value > 0) {
        counter.value--;
    }
}
function increment() {
    counter.value++;
}
</script>
<template>
    <div class="flex-col bg-stone-100 rounded py-8 px-6 w-96 shadow-md flex items-center">
        <div class="relative ">
            <img class="size-32 rounded-full" src="https://www.abopr.org.br/site/wp-content/uploads/2022/01/4-1.jpg" alt="foto de perfil">
            <div v-show="counter > 0" class="absolute top-0 right-0 flex justify-center items-center size-6 rounded-full bg-red-600 text-white">
                {{ counter }}
            </div>
        </div>
        <p v-if="counter > 0" class="bg-stone-300 px-3 rounded-lg mt-2">¡Tienes nuevos mensajes! </p>
        <p v-else class="bg-stone-300 px-3 rounded-lg mt-2">¡Nadie te habla! </p>

        <div class="mt-2">
            Maria Camila Avendaño Días
        </div>

        <div class="flex justify-around w-24 mt-4">
            <button @click="decrement" class="text-white bg-cyan-900 rounded px-2 w-6 flex justify-center items-center">-</button>
            {{ counter }}
            <button @click="increment" class="text-white bg-cyan-900 rounded px-2 w-6 flex justify-center items-center">+</button>
        </div>
    </div>
</template>