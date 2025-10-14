<script setup>
import { ref } from 'vue'

const arreglo = ref([
  {
    id: 1,
    fecha: '2025',
    titulo: 'Certificación DevOps y Full Stack',
    descripcion: 'Especialización en arquitectura de software, CI/CD, y despliegue con Docker y Kubernetes.',
    enlace: 'https://ejemplo.com/devops',
    accentColor: '#2A9D8F'
  },
  {
    id: 2,
    fecha: '2024',
    titulo: 'Técnico Universitario en Programación',
    descripcion: 'Desarrollo avanzado con Vue.js, React, TypeScript y PostgreSQL.',
    enlace: 'https://ejemplo.com/programacion',
    accentColor: '#F4A261'
  },
  {
    id: 3,
    fecha: '2023',
    titulo: 'Técnico en Desarrollo Back-End',
    descripcion: 'Dominio de Node.js, Express y MongoDB. Creación de APIs seguras.',
    enlace: 'https://ejemplo.com/backend',
    accentColor: '#E76F51'
  },
  {
    id: 4,
    fecha: '2022',
    titulo: 'Fundamentos de Desarrollo Web',
    descripcion: 'Primeros pasos con HTML, CSS, JavaScript y diseño responsivo.',
    enlace: 'https://ejemplo.com/web',
    accentColor: '#264653'
  }
])
</script>

<template>
  <div class="timeline-container">
    <h1>Mi Camino como Desarrollador Full Stack</h1>
    <ul>
      <li v-for="item in arreglo" :key="item.id" :style="`--accent-color: ${item.accentColor}`">
        <div class="date">{{ item.fecha }}</div>
        <div class="title">{{ item.titulo }}</div>
        <div class="descr">{{ item.descripcion }}</div>
        <a :href="item.enlace" target="_blank" class="enlace">Ver más</a>
      </li>
    </ul>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap");

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.timeline-container {
  --color: rgba(30, 30, 30);
  /*--bgColor: rgba(245, 245, 245);*/
  min-height: 100vh;
  display: grid;
  align-content: center;
  gap: 2rem;
  padding: 2rem;
  font-family: "Poppins", sans-serif;
  color: var(--color);
  /*background: linear-gradient(135deg, #f8f9fa, #e9ecef);*/
}

h1 {
  text-align: center;
  font-size: 2.2rem;
  font-weight: 700;
  color: #2c3e50;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

ul {
  --col-gap: 2rem;
  --row-gap: 2rem;
  --line-w: 0.3rem;
  display: grid;
  grid-template-columns: var(--line-w) 1fr;
  grid-auto-columns: max-content;
  column-gap: var(--col-gap);
  list-style: none;
  width: min(60rem, 90%);
  margin-inline: auto;
}

ul::before {
  content: "";
  grid-column: 1;
  grid-row: 1 / span 20;
  background: linear-gradient(to bottom, #2c3e50, #3498db);
  border-radius: calc(var(--line-w) / 2);
}

ul li:not(:last-child) {
  margin-bottom: var(--row-gap);
}

ul li {
  grid-column: 2;
  --inlineP: 1.5rem;
  margin-inline: var(--inlineP);
  grid-row: span 2;
  display: grid;
  grid-template-rows: min-content min-content min-content min-content;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

ul li:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

ul li .date {
  --dateH: 3.5rem;
  height: var(--dateH);
  margin-inline: calc(var(--inlineP) * -1);
  text-align: center;
  background: linear-gradient(135deg, var(--accent-color), color-mix(in srgb, var(--accent-color) 70%, #000));
  color: white;
  font-size: 1.3rem;
  font-weight: 700;
  display: grid;
  place-content: center;
  position: relative;
  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease;
}

ul li .date:hover {
  transform: scale(1.1);
}

ul li .date::before {
  content: "";
  width: var(--inlineP);
  aspect-ratio: 1;
  background: var(--accent-color);
  background-image: linear-gradient(rgba(0, 0, 0, 0.3) 100%, transparent);
  position: absolute;
  top: 100%;
  clip-path: polygon(0 0, 100% 0, 0 100%);
  right: 0;
}

ul li .date::after {
  content: "";
  position: absolute;
  width: 2.2rem;
  aspect-ratio: 1;
  background: var(--bgColor);
  border: 0.3rem solid var(--accent-color);
  border-radius: 50%;
  top: 50%;
  transform: translate(50%, -50%);
  right: calc(100% + var(--col-gap) + var(--line-w) / 2);
}

ul li .title,
ul li .descr,
ul li .enlace {
  background: linear-gradient(145deg, #122b4b, #1c354e);
  position: relative;
  padding-inline: 1.5rem;
  border-radius: 8px;
}

ul li .title {
  padding-block-start: 1.5rem;
  padding-block-end: 1rem;
  font-weight: 500;
  font-size: 1.3rem;
  color: #dfe2e6;
}

ul li .descr {
  padding-block-end: 1rem;
  font-weight: 300;
  color: #e3e6e9;
  line-height: 1.6;
}

ul li .enlace {
  display: inline-block;
  padding: 0.6rem 1.2rem;
  background: linear-gradient(135deg, var(--accent-color), color-mix(in srgb, var(--accent-color) 70%, #000));
  color: white;
  text-decoration: none;
  border-radius: 25px;
  font-weight: 500;
  margin-bottom: 1.5rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

ul li .enlace:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
}

ul li .title::before,
ul li .descr::before {
  content: "";
  position: absolute;
  width: 90%;
  height: 0.5rem;
  background: rgba(0, 0, 0, 0.4);
  left: 50%;
  border-radius: 50%;
  filter: blur(4px);
  transform: translate(-50%, 50%);
}

ul li .title::before {
  bottom: calc(100% + 0.125rem);
}

ul li .descr::before {
  z-index: -1;
  bottom: 0.25rem;
}

@media (min-width: 40rem) {
  ul {
    grid-template-columns: 1fr var(--line-w) 1fr;
  }
  ul::before {
    grid-column: 2;
  }
  ul li:nth-child(odd) {
    grid-column: 1;
  }
  ul li:nth-child(even) {
    grid-column: 3;
  }
  ul li:nth-child(2) {
    grid-row: 2/4;
  }
  ul li:nth-child(odd) .date::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%);
    left: 0;
  }
  ul li:nth-child(odd) .date::after {
    transform: translate(-50%, -50%);
    left: calc(100% + var(--col-gap) + var(--line-w) / 2);
  }
  ul li:nth-child(odd) .date {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
  }
}

.credits {
  margin-top: 1.5rem;
  text-align: right;
  font-size: 0.9rem;
  color: #2c3e50;
}

.credits a {
  color: #2c3e50;
  text-decoration: none;
  transition: color 0.3s ease;
}

.credits a:hover {
  color: #3498db;
}
</style>
