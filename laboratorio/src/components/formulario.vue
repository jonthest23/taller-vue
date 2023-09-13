<template>
    <form @submit.prevent="agregarDato">
      <input v-model="articulo" type="text" placeholder="articulo" />
      <input placeholder="cantidad" v-model="cantidad"/>
      <input placeholder="valor" v-model = "valor"/>
      <input placeholder="VU" v-model = "vu"/>
      <input placeholder="total" v-model="total"/>

      <button type="submit">Agregar</button>
    </form>
  </template>
  
  <script lang="ts">
  export default {
    data() {
      return {
        nuevoDato: {
            articulo: '',
            cantidad: '',
            vu: '',
            valor: '',
            total: '',
        },
        articulo: '',
        cantidad: '',
        valor: '',
        vu: '',
        total: '',
      };
    },
    methods: {
      agregarDato() {
        if (this.nuevoDato) {
          this.$emit('nuevo-dato', this.nuevoDato);
          this.nuevoDato = {
            articulo: this.articulo,
            cantidad: this.cantidad,
            vu: this.vu,
            valor: this.valor,
            total: this.total,
          }; 
        }
      },
    },
  };
  </script>