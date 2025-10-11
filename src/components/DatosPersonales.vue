<script setup>
const title = 'Martín Moreno';
const descripcion = 'Técnico Universitario en Programación - UTN';
const residencia = 'San Rafael, Mendoza, Argentina';
const presentacion = 'Hola, Bienvenido a mi portafolio de proyectos. Soy un desarrollador web con experiencia en el desarrollo de aplicaciones web y móviles.';
const redesSociales = [
  { id: 1, name: 'linkedin', src: '/src/assets/linkedin_.svg', url: 'https://www.linkedin.com/in/jose-perez/' },
  { id: 2, name: 'instagram', src: '/src/assets/instagram_.svg', url: 'https://www.instagram.com/joseperez/' },
  { id: 3, name: 'github', src: '/src/assets/github_.svg', url: '' },
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
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 2rem;
  background: linear-gradient(135deg, #1a2a3a 0%, #0f1424 100%);
}

/* Contenedor más angosto y centrado */
.contenido {
  max-width: 500px; /* 🔹 hacelo más o menos angosto cambiando este valor */
  width: 100%;
}

/* Título principal (nombre) */
h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: #ffffff;
  text-shadow: 0 2px 10px rgba(255, 255, 255, 0.1);
  transition: all 0.4s ease; /* transición suave */
}

/* Efecto de brillo al pasar el mouse */
h1:hover {
  color: #64b5f6;
  text-shadow: 0 0 10px #64b5f6, 0 0 20px #64b5f6, 0 0 30px #64b5f6;
  transform: scale(1.05);
}

/* Subtítulo */
h2 {
  font-size: 1.3rem;
  font-weight: 500;
  margin-bottom: 1.5rem;
  color: #64b5f6;
  letter-spacing: 0.5px;
}

p {
  font-size: 1.1rem;
  line-height: 1.7;
  margin-bottom: 2rem;
  color: #e0e0e0;
}

/* Íconos */
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
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.container-lista a:hover {
  background: rgba(100, 181, 246, 0.2);
  border-color: #64b5f6;
  box-shadow: 0 0 20px rgba(100, 181, 246, 0.3);
}

/* Íconos SVG */
.icon-redsocial {
  width: 28px;
  height: 28px;
  transition: filter 0.3s ease;
}

.container-lista a:hover .icon-redsocial {
  filter: brightness(0) invert(1) drop-shadow(0 0 5px rgba(100, 181, 246, 0.5));
}

/* Subtítulos */
h3 {
  font-size: 1.1rem;
  font-weight: 600;
  margin-top: 2rem;
  margin-bottom: 0.5rem;
  color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
}

h4 {
  font-size: 1rem;
  font-weight: 400;
  color: #9e9e9e;
  margin-top: 0.5rem;
  text-align: center;
}

/* Responsive */
@media (max-width: 768px) {
  h1 {
    font-size: 2rem;
  }

  h2 {
    font-size: 1.1rem;
  }

  p {
    font-size: 1rem;
  }

  .container-lista {
    justify-content: center;
  }
}
</style>
