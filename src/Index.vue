<template>
  <div class="responsive-div">
    <NavBar />
    <div class="search-container">
        <form action="/action_page.php">
            <input type="text" placeholder="Buscar..." name="search">
            <button type="submit">
                <img src="/public/busqueda.png" alt="Buscar">
            </button>
        </form>
    </div>
    <div class="container">
    <h1>Fast Food Express</h1>
    <p>Somos una empresa de comida rápida comprometida en brindar alimentos deliciosos y de alta calidad a nuestros clientes. Con más de 10 años de experiencia en la industria, nos enorgullece ofrecer una amplia variedad de opciones para satisfacer todos los antojos.</p>
    <p>Nuestro menú incluye hamburguesas jugosas, papas fritas crujientes, pollo frito irresistible, sándwiches sabrosos y mucho más. Trabajamos con ingredientes frescos y seleccionamos cuidadosamente cada uno para garantizar la frescura y el sabor en cada bocado.</p>
    <p>En Fast Food Express, nos esforzamos por brindar un excelente servicio al cliente. Nuestro equipo amable y capacitado está listo para atender tus necesidades y asegurarse de que tu experiencia sea inolvidable. Ya sea que estés buscando un almuerzo rápido, una cena informal o simplemente algo delicioso para llevar, estamos aquí para servirte.</p>
    <p>Visítanos en cualquiera de nuestras ubicaciones convenientes y descubre por qué somos la elección preferida de los amantes de la comida rápida. ¡Esperamos con ansias servirte y brindarte una comida sabrosa y satisfactoria!</p>
  </div>
    <h1>Platos Estrella</h1>
      <section class="carousel" aria-label="Gallery">
        <ol class="carousel__viewport">
          <li id="carousel__slide1"
              tabindex="0"
              class="carousel__slide">
            <div class="carousel__snapper">
              <img src="/public/sushi.jpg" alt="Descripción de la imagen 1">
              <a href="#carousel__slide4"
                class="carousel__prev">Go to last slide</a>
              <a href="#carousel__slide2"
                class="carousel__next">Go to next slide</a>
            </div>
          </li>
          <li id="carousel__slide2"
              tabindex="0"
              class="carousel__slide">
            <div class="carousel__snapper">
              <img src="/public/sushi.jpg" alt="Descripción de la imagen 2">
            </div>
            <a href="#carousel__slide1"
              class="carousel__prev">Go to previous slide</a>
            <a href="#carousel__slide3"
              class="carousel__next">Go to next slide</a>
          </li>
          <li id="carousel__slide3"
              tabindex="0"
              class="carousel__slide">
            <div class="carousel__snapper">
              <img src="/public/sushi.jpg" alt="Descripción de la imagen 3">
            </div>
            <a href="#carousel__slide2"
              class="carousel__prev">Go to previous slide</a>
            <a href="#carousel__slide4"
              class="carousel__next">Go to next slide</a>
          </li>
          <li id="carousel__slide4"
              tabindex="0"
              class="carousel__slide">
            <div class="carousel__snapper">
              <img src="/public/sushi.jpg" alt="Descripción de la imagen 4">
            </div>
            <a href="#carousel__slide3"
              class="carousel__prev">Go to previous slide</a>
            <a href="#carousel__slide1"
              class="carousel__next">Go to first slide</a>
          </li>
        </ol>
      </section>
      <h1>Platos Recomendados</h1>
      <div class="card-container responsive-div">
        <CardCompra v-for="(item, index) in productos" :key="index" :producto="item" />
      </div>
    <Footer />
  </div>
  
</template>

<script setup lang="ts">
import { ref } from 'vue';
import NavBar from './components/NavBar.vue';
import CardCompra from './components/CardCompra.vue';
import Footer from './components/Footer.vue';

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
  {
    name: 'sushi',
    description: 'Tiene unas ricas salteado de verduras con gamabas increibles',
    img: '/public/sushi.jpg',
  },
]);



</script>

