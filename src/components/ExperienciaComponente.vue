<script setup>
import img01 from '/src/components/icons/ventas.svg'
import img02 from '/src/components/icons/ecommerce.svg'
import img03 from '/src/components/icons/configuracion.svg'
import img04 from '/src/components/icons/uiux.svg'
import img05 from '/src/components/icons/watch_.svg'
import {ref} from 'vue';
const titulo='Mi experiencia';
const fecha='Desde Enero 2020 / Noviembre 2025';
const experiencias = ref([
    {id:1, icono: img01, parrafo: "Lideré un equipo de 5 desarrolladores en la creación de una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el primer año"},
    {id:2, icono: img02, parrafo: 'Diseñé y desarrollé una aplicación web utilizando Node.js, React y MongoDB, logrando reducir el tiempo de carga de las páginas en un 50%'},
    {id:3, icono: img03, parrafo: 'Implementé soluciones de autenticación y autorización, mejorando la seguridad del sitio web y reduciendo los intentos de acceso no autorizado en un 20%.'},
    {id:4, icono: img04, parrafo: 'Colaboré con diseñadores de UX/UI para crear interfaces de usuario atractivas y fáciles de usar, aumentando la satisfacción del cliente en un 15%.'},
    {id:5, icono: img05, parrafo: 'Automaticé procesos de despliegue continuo utilizando Jenkins y Docker, reduciendo los tiempos de despliegue en un 40%.'}
]);
</script>
<template>
  <div class="card">
    <h3 class="titulo">{{ titulo }}</h3>
    <p class="fecha">{{ fecha }}</p>
    <ul class="listado">
      <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
        <img class="imagen-svg" :src="experiencia.icono" width="45rem" :alt="experiencia.parrafo">
        <p>{{ experiencia.parrafo }}</p>
      </li>
      <!-- <li class="item"><img class="imagen-svg" src="/src/assets/ventas.svg" width="45rem" alt="">
        <p>Lideré un equipo de 5 desarrolladores en la creación de una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el primer año.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/ecomerce.svg" width="45rem" alt="">
        <p>Diseñé y desarrollé una aplicación web utilizando Node.js, React y MongoDB, logrando reducir el tiempo de carga de las páginas en un 50%.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/configuracion.svg" width="45rem" alt="">
        <p>Implementé soluciones de autenticación y autorización, mejorando la seguridad del sitio web y reduciendo los intentos de acceso no autorizado en un 20%.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/uiux.svg" width="45rem" alt="">
        <p>Colaboré con diseñadores de UX/UI para crear interfaces de usuario atractivas y fáciles de usar, aumentando la satisfacción del cliente en un 15%.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/watch.svg" width="45rem" alt="">
        <p>Automaticé procesos de despliegue continuo utilizando Jenkins y Docker, reduciendo los tiempos de despliegue en un 40%.</p>
      </li> -->
    </ul>
  </div>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  padding: 3rem;
  background: linear-gradient(135deg, #2a3b4c 0%, #3e5a7a 100%);
  border-radius: 25px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.35);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  max-width: 800px; /* Aumentado para más espacio */
  width: 90%; /* Más flexible en pantallas pequeñas */
  margin: 2rem auto;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.5);
}

.titulo {
  font-size: 2.25rem; /* Más grande para destacar */
  font-weight: 700;
  color: #ff8c66; /* Coral más brillante */
  text-align: center;
  margin-bottom: 1rem;
  letter-spacing: 1px;
  position: relative;
  overflow: hidden;
  transition: color 0.3s ease;
}

.titulo::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(to right, transparent, #fff, transparent);
  transition: left 0.5s ease;
}

.titulo:hover::after {
  left: 100%; /* Efecto de brillo al pasar el mouse */
}

.titulo:hover {
  color: #fff; /* Cambio de color al pasar el mouse */
    text-shadow: 0 0 10px #64b5f6, 0 0 20px #64b5f6, 0 0 30px #64b5f6;
  transform: scale(1.05);
}

.fecha {
  font-size: 1.25rem; /* Aumentado para mejor legibilidad */
  color: #e0d6d2; /* Tono más claro y elegante */
  text-align: center;
  margin-bottom: 2rem;
  font-style: italic;
  opacity: 0.95;
}

.listado {
  display: flex;
  flex-direction: column;
  gap: 1rem; /* Más espacio entre ítems */
}

.item {
  display: flex;
  align-items: center;
  padding: 1.5rem;
  gap: 2rem;
  background-color: rgba(255, 255, 255, 0.08);
  border-radius: 15px;
  transition: background-color 0.3s ease, transform 0.2s ease;
  font-size: 1.1rem; /* Texto más grande */
}

.item:hover {
  background-color: rgba(255, 255, 255, 0.15);
  transform: scale(1.02); /* Ligeramente más grande al pasar el mouse */
}

/* Media query para pantallas más pequeñas */
@media (max-width: 600px) {
  .card {
    padding: 2rem;
    width: 95%;
  }
  .titulo {
    font-size: 1.75rem;
  }
  .fecha {
    font-size: 1rem;
  }
  .item {
    padding: 1rem;
    gap: 1rem;
    font-size: 1rem;
  }
}
</style>