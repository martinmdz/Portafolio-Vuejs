<script setup>
const title = 'Martín Moreno';
const descripcion = 'Técnico Universitario en Programación - UTN';
const residencia = 'San Rafael, Mendoza, Argentina';
const presentacion = 'Bienvenido/a a mi portafolio de proyectos. Soy un estudiante de programación con gran motivación por el desarrollo de aplicaciones [web/móviles]. Aquí presento mis proyectos más recientes, una muestra de mi aprendizaje constante y la aplicación práctica de mis conocimientos.';
const redesSociales = [
  { id: 1, name: 'linkedin', src: '/src/assets/linkedin_.svg', url: 'https://www.linkedin.com/in/mart%C3%ADn-moreno-olgu%C3%ADn-29821836b/' },
  { id: 2, name: 'instagram', src: '/src/assets/instagram_.svg', url: 'https://www.instagram.com/joseperez/' },
  { id: 3, name: 'github', src: '/src/assets/github_.svg', url: 'https://github.com/martinmdz/' },
  { id: 4, name: 'curriculum', src: '/src/assets/curriculum_.svg', url: '' },
];
const telefono = '+54 9 2604-409428';
</script>

<template>
  <section class="datos-personales">
    <div class="card">
      <h1>{{ title }}</h1>
      <h2>{{ descripcion }}</h2>
      <p>{{ presentacion }}</p>
      <ul class="container-lista">
        <li v-for="red in redesSociales" :key="red.id">
          <a :href="red.url"><img class="icon-redsocial" :src="red.src" width="35rem" :alt="red.name"></a>
        </li>
      </ul>
      <h3>📞 Mi Teléfono personal: {{ telefono }}</h3>
      <h4>{{ residencia }}</h4>
    </div>
  </section>
</template>

<style scoped>
.datos-personales {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 3rem 1rem;
  min-height: 100vh;
  /* QUITAMOS TODO ESTO: */
  /* background-image, background-color, ::before, position, z-index */
}

/* EFECTO CRISTAL SUAVE (solo en la tarjeta) */
.card {
  max-width: 700px;
  width: 100%;
  padding: 2.5rem;
  background: rgba(255, 255, 255, 0.08);
  border-radius: 20px;
  border: 1px solid rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  /* box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3); */
  transition: all 0.4s ease;
}

/* .card:hover {
  background: rgba(255, 255, 255, 0.12);
  transform: translateY(-5px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.4);
} */

/* Títulos */
h1 {
  font-size: 2.8rem;
  font-weight: 700;
  margin: 0 0 0.5rem;
  color: #ffffff;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
  transition: all 0.4s ease;
}

h1:hover {
  color: #64b5f6;
  text-shadow: 0 0 15px #64b5f6, 0 0 30px #64b5f6;
  transform: scale(1.03);
}

h2 {
  font-size: 1.4rem;
  color: #64b5f6;
  margin-bottom: 1.5rem;
  font-weight: 500;
}

p {
  font-size: 1.1rem;
  line-height: 1.8;
  color: #e0e0e0;
  margin-bottom: 2rem;
}

/* Redes */
.container-lista {
  list-style: none;
  padding: 0;
  margin: 2rem 0;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.container-lista a {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.container-lista a:hover {
  background: rgba(100, 181, 246, 0.2);
  border-color: #64b5f6;
  box-shadow: 0 0 20px rgba(100, 181, 246, 0.3);
  transform: scale(1.1);
}

.icon-redsocial {
  width: 28px;
  height: 28px;
  filter: brightness(0.9);
  transition: filter 0.3s ease;
}

.container-lista a:hover .icon-redsocial {
  filter: brightness(0) invert(1) drop-shadow(0 0 8px #64b5f6);
}

h3, h4 {
  margin: 1rem 0;
  color: #ffffff;
}

h3 {
  font-size: 1.2rem;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

h4 {
  font-size: 1rem;
  color: #bbbbbb;
}

/* Responsive */
@media (max-width: 768px) {
  .card {
    padding: 2rem;
    margin: 1rem;
  }
  h1 { font-size: 2.2rem; }
  h2 { font-size: 1.2rem; }
}
</style>
