<template>
  <section class="intereses">
    <!-- Fondo animado solo aquí -->
    <div class="fondo-lava">
      <FondoLava />
    </div>

    <div class="contenido">
      <ul class="lista">
        <li v-for="interes in intereses" :key="interes" class="item">
          {{ interes }}
        </li>
      </ul>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import FondoLava from './FondoLava.vue';

const intereses = ref([
  'Aprender Nuevas Tecnologías: Estoy constantemente estudiando frameworks como Vue.js, Node.js y bases de datos (PostgreSQL, MongoDB) para crear aplicaciones web completas y escalables.',
  'Reparación y Armado de Equipos: Me apasiona ensamblar PCs personalizadas, diagnosticar fallas de hardware y optimizar sistemas para gaming o desarrollo.',
  'Emprendimiento Local: Aplico mis conocimientos en administración para ayudar a comercios de San Rafael a digitalizarse: sitios web, sistemas de stock y ventas online.',
  'Automatización de Tareas: Desarrollo scripts simples (Bash, Python) para agilizar el diagnóstico de celulares y PCs en mi servicio técnico, ahorrando tiempo a clientes.',
  'Fotografía y Edición: Capturo momentos del día a día en Mendoza y edito con herramientas gratuitas como GIMP, aplicando lo aprendido en diseño web para mejorar la presentación visual.'
]);
</script>

<style scoped>
.intereses {
  position: relative;
  margin: 4rem 0;
  padding: 3rem 1rem;
  overflow: hidden;
  border-radius: 20px;
}

/* FONDO ANIMADO (solo en esta sección) */
.fondo-lava {
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  z-index: 1;
  pointer-events: none;
  overflow: hidden;
}

.fondo-lava > * {
  width: 100%;
  height: 100%;
}

/* CONTENIDO ENCIMA */
.contenido {
  position: relative;
  z-index: 2;
  max-width: 900px;
  margin: 0 auto;
  background: rgba(0, 0, 0, 0.4);
  padding: 2.5rem;
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
}

.lista {
  list-style: none;
  padding: 0;
  margin: 0;
  color: #f0f0f0;
  font-size: 1.35rem;
  line-height: 1.8;
}

.item {
  margin-bottom: 1.5rem;
  padding-left: 1.5rem;
  position: relative;
}

.item::before {
  content: '→';
  position: absolute;
  left: 0;
  color: #64b5f6;
  font-weight: bold;
}

/* Responsive */
@media (max-width: 768px) {
  .contenido {
    padding: 2rem;
  }
  .lista {
    font-size: 1.2rem;
  }
}
</style>