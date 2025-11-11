<template>
  <div class="container">
    <header id="top">
      <NavBar />
      <DatosPersonales />
    </header>

    <main>
      <section id="educacion">
        <h2>Educación - Cursos</h2>
        <EducacionComponente />
      </section>
      <section id="experiencia">
        <h2>Experiencia</h2>
        <ExperienciaComponente />
      </section>
      <section id="proyectos">
        <h2>Proyectos</h2>
        <ProyectosComponente />
      </section>
      <section id="habilidades">
        <h2>Habilidades</h2>
        <HabilidadesComponente />
      </section>
      <section id="intereses">
        <h2>Intereses</h2>
        <InteresesComponente />
      </section>
    </main>

    <footer>
      <a href="#top">Inicio</a>
      <br>
      <a href="#educacion">Educación</a>
      <p>2025 Martín Moreno - Portafolio web</p>
    </footer>
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import EducacionComponente from './components/EducacionComponente.vue';
import ExperienciaComponente from './components/ExperienciaComponente.vue';
import ProyectosComponente from './components/ProyectosComponente.vue';
import HabilidadesComponente from './components/HabilidadesComponente.vue';
import InteresesComponente from './components/InteresesComponente.vue';
</script>

<style scoped>
.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 2rem 1rem;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* QUITA FONDOS DE TODOS LOS ELEMENTOS */
header, main, section, footer {
  background: transparent !important;
  backdrop-filter: none !important;
  border: none !important;
  box-shadow: none !important;
  padding: 0 !important;
  margin: 0 !important;
}

/* Solo un poco de espacio entre secciones */
section {
  margin-bottom: 4rem;
  padding: 2rem;
}

/* EFECTO CRISTAL SUAVE (opcional, pero SIN BLUR) */
section > * {
  background: rgba(27, 26, 26, 0.08);
  padding: 2rem;
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(6px);
  -webkit-backdrop-filter: blur(6px);
}

h2 {
  color: #64b5f6;
  text-align: center;
  margin: 0 0 1.5rem 0;
  font-size: 2rem;
}

/* EMPUJA EL FOOTER AL FINAL */
main {
  flex: 1; /* ← CLAVE */
}

footer {
  margin-top: auto;
  padding: 2rem 0;
  text-align: center;
  color: white;
  background: rgba(0, 0, 0, 0.3);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 12px 12px 0 0;
}

footer a {
  color: #64b5f6;
  text-decoration: none;
  margin: 0 1em;
  font-weight: bold;
  font-size: 1.5em;
  transition: all 0.4s ease;
}

footer a:hover {
  color: #bbdefb;
  text-shadow: 0 0 20px #64b5f6;
  transform: scale(1.05);
}

footer p {
  margin: 1rem 0 0;
  font-size: 1em;
  opacity: 0.9;
}
</style>