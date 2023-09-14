<script lang="ts">

import formulario from './components/formulario.vue';
import tabla from './components/tabla.vue';
import { defineComponent } from 'vue';



export default defineComponent({
  data() {
    return {
      datos: Array<any>(),
      total: 0,
      descuento: ""
    };
  },
  components: {
    formulario,
    tabla
  },
  methods: {
    agregarDatoATabla(nuevoDato: any) {
      if (this.datos.some((dato:any) => dato.id === nuevoDato.id)) {
        alert('El id ya existe')
      } else {
        try {
          this.datos.push(nuevoDato);
        } catch (error) {
          alert('Error al agregar el dato');
          console.log(error);
        }
        this.verificardescuento()
      }
    },
    verificardescuento(): void {
      let total = this.calcularTotal()
      if(this.calcularCantidad() >= 12){
        total = total - total * 0.2
        this.descuento = '20% off'
      }else if(total >= 240000){
        total = total - total * 0.15
        this.descuento = '15% off'
      }else if(total >= 120000 || this.calcularCantidad() >= 6){
        total = total - total * 0.1
        this.descuento = '10% off'
      }else if (total >= 60000) {
        total = total - total * 0.05
        this.descuento = '5% off'
      }
      this.total = total
    },
    calcularTotal() {
      let total = 0
      for (let i = 0; i < this.datos.length; i++) {
        total += this.datos[i].total
      }
      return total
      
    },
    calcularCantidad() {
      let cantidad = 0
      for (let Item in this.datos){
        cantidad += this.datos[Item].cantidad
      }
      return cantidad
  },
}
})
</script>

<template>
  <formulario @nuevo-dato="agregarDatoATabla" />
  <tabla :datos="datos" :total = "total" :descuento = "descuento"/>
</template>


