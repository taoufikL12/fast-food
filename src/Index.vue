<template>
  <div class="responsive-div">
    <NavBar />
    <h1>Platos Recomendados</h1>

    <div class="card-container responsive-div">
      <CardCompra v-for="(item, index) in productos" :key="index" :producto="item" />
    </div>

  </div>
  
</template>

<script setup lang="ts">
import { ref } from 'vue';
import NavBar from './components/NavBar.vue';
import CardCompra from './components/CardCompra.vue';

const productos = ref([
  {
    name: 'Ensala De Espinacas',
    description: 'Ensalda Realizada con ingredietendes Japoneses Rica en vitamina',
    img: '/public/rabbit-food.jpg',
  },
  {
    name: 'Quesadillas',
    description: 'Esta hecha de unas ricas verduras mejicanas y una gran salsa jugosa',
    img: '/public/quesadillas.jpg',
  },
  {
    name: 'sushi',
    description: 'Tiene unas ricas salteado de verduras con gamabas increibles',
    img: '/public/sushi.jpg',
  },
]);

</script>

