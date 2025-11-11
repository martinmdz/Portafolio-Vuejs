<script>
</script>

<template>
<!-- <body>
  <div>
     <div class="wave"></div>
     <div class="wave"></div>
     <div class="wave"></div>
  </div>
</body> -->

  <div class="waves-section-wrapper">
     <div class="waves-container">
         <div class="wave"></div>
         <div class="wave"></div>
         <div class="wave"></div>
     </div>
     
     <div class="section-content">
         </div>
  </div>

</template>

<style scoped>
/* 1. Estilo del Contenedor Principal (Reemplaza el estilo de body) */
.waves-section-wrapper {
    position: absolute; /* Clave para que .wave (absolute) se posicione dentro */
    margin: 0 auto;
    width: 100%;
    /* Define la altura de la sección. ¡Ajusta este valor! */
    height: 500px; 
    overflow: hidden; /* Asegura que la animación que se sale (200% width) no cause barras de desplazamiento */
    
    /* Mueve los estilos de fondo y animación del body aquí: */
    font-family: -apple-system, BlinkMacSystemFont, sans-serif;
    background: linear-gradient(315deg, rgba(101,0,94,1) 3%, rgba(60,132,206,1) 38%, rgba(48,238,226,1) 68%, rgba(255,25,25,1) 98%);
    animation: gradient 15s ease infinite;
    background-size: 400% 400%;
    /* No uses 'background-attachment: fixed' si no quieres que el fondo se mueva con el scroll global */
}

@keyframes gradient {
    0% {
        background-position: 0% 0%;
    }
    50% {
        background-position: 100% 100%;
    }
    100% {
        background-position: 0% 0%;
    }
}


.waves-container {
    /* Contenedor de las olas, asegura que cubra la sección */
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1; /* Lo ponemos en la capa de fondo */
}

/* 2. Estilo de las Olas (Cambia fixed a absolute) */
.wave {
    background: rgb(255 255 255 / 25%);
    border-radius: 1000% 1000% 0 0;
    /* 💥 CAMBIO CLAVE: position: absolute 💥 */
    position: absolute; 
    width: 200%;
    height: 12em;
    animation: wave 10s -3s linear infinite;
    transform: translate3d(0, 0, 0);
    opacity: 0.8;
    bottom: 0;
    left: 0;
    /* 💥 z-index: -1 ya no funciona bien con absolute. Ajusta el z-index de toda la capa */
    /* Lo quitamos y usamos z-index en .waves-container */
}

.wave:nth-of-type(2) {
    bottom: -1.25em;
    animation: wave 18s linear reverse infinite;
    opacity: 0.8;
}

.wave:nth-of-type(3) {
    bottom: -2.5em;
    animation: wave 20s -1s reverse infinite;
    opacity: 0.9;
}

@keyframes wave {
    2% {
        transform: translateX(1);
    }

    25% {
        transform: translateX(-25%);
    }

    50% {
        transform: translateX(-50%);
    }

    75% {
        transform: translateX(-25%);
    }

    100% {
        transform: translateX(1);
    }

}

/* 3. Estilo del Contenido (Para que el texto esté visible encima) */
.section-content {
    position: relative; /* Clave para que el z-index funcione */
    z-index: 2; /* Mayor que el z-index: 1 del fondo */
    padding: 20px;
    /* ... otros estilos para el texto ... */
}
</style>