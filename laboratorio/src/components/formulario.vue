<template>
  <form @submit.prevent="agregarDato">
    <input type="number" placeholder="id" v-model="id" />
    <input type="text" placeholder="articulo" v-model="articulo" />
    <input placeholder="cantidad" v-model="cantidad" />
    <input placeholder="valor" v-model="valor" />
    <input placeholder="VU" v-model="vu" />
    <input placeholder="total" v-model="total" />

    <button type="submit">Agregar</button>
  </form>
</template>
  


<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      id: '',
      articulo: '',
      cantidad: '',
      vu: '',
      valor: '',
      total: '',
      nuevoDato: {},
    };

  },
  methods: {
    agregarDato() {

      if (this.id == '' || this.articulo == '' || this.cantidad == '' || this.vu == '' || this.valor == '' || this.total == '') {
        alert('Por favor llene todos los campos')
        return
      } else {
        this.nuevoDato = {
          id: this.id,
          articulo: this.articulo,
          cantidad: this.cantidad,
          vu: this.vu,
          valor: this.valor,
          total: this.total,
        };
        this.$emit('nuevo-dato', this.nuevoDato);
        this.nuevoDato = ''; // Limpiar el campo después de emitir el evento
      }
    },

  },
}

)
</script>