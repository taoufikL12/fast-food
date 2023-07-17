<template>
    <div class="card">
        <img class="card-img" :src="producto.img" alt="Imagen de la tarjeta">
        <div class="card-content">
            <h2 class="card-title">{{ producto.name }}</h2>
            <p class="card-description">{{ producto.description }}</p>
        </div>
        <hr class="divider" />
        <button class="blue-button">Pedir</button>
    </div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  producto: Object
})
</script>

