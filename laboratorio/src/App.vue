<script lang="ts">

import formulario from './components/formulario.vue';
import tabla from './components/tabla.vue';
import { defineComponent } from 'vue';



export default defineComponent({
  data() {
    return {
      datos: [{}],
    };
  },
  components: {
    formulario,
    tabla
  },
  methods: {
    agregarDatoATabla(nuevoDato: object) {
      try {
        this.datos.push(nuevoDato);
      } catch (error) {
        alert('Error al agregar el dato');
        console.log(error);
      }
  }
  },
})
</script>

<template>
    <formulario @nuevo-dato="agregarDatoATabla"/>
    <tabla :datos="datos" />
</template>


