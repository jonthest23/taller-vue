<template>
  <form @submit.prevent="agregarDato">
    <input type="number" placeholder="id" v-model="id" />
    <input type="text" placeholder="articulo" v-model="articulo" />
    <input placeholder="cantidad" v-model="cantidad" />
    <input placeholder="VU" v-model="vu" />
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
      nuevoDato: {},
    };

  },
  methods: {
    soloNumero(){
     return /^[0-9]+$/.test(this.id) && /^[0-9]+$/.test(this.cantidad) && /^[0-9]+$/.test(this.vu)
    },

    agregarDato(): void {

      if (this.id == '' && this.articulo == '' && this.cantidad == '' && this.vu == '' && this.soloNumero()) {
        alert('Por favor llene todos los campos y solo numeros en los campos numericos')
        
      }else if(parseInt(this.cantidad)<0){
        alert('La cantidad debe ser mayor a 0')
        
      }
      else {
        this.nuevoDato = {
          id: parseInt(this.id),
          articulo: this.articulo,
          cantidad: parseInt(this.cantidad),
          vu: parseInt(this.vu),
          total: parseInt(this.cantidad) * parseInt(this.vu),
        };
        this.$emit('nuevo-dato', this.nuevoDato);
        this.nuevoDato = {};
      }
    },

  },
}

)
</script>