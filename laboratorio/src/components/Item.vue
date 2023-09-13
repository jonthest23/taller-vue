<script lang="ts">
export default {
  data() {
    return {
      datos: [], // Inicializa un arreglo para almacenar los datos
    };
  },
  methods: {
    agregarNuevoDato(nuevoDato) {
      this.datos.push(nuevoDato); // Agrega el nuevo dato al arreglo de datos
    },
  },
};
</script>

<template>
  <div class="item">
    <div class="item__container">
      <div class="item__container__item">
        <h4>Articulo</h4>
        <h4>Cantidad</h4>
        <h4>Valor</h4>
        <h4>Total</h4>
      </div>
      <div class="item__container__item" v-for="item in datos" :key="item.id">
        <p>{{item.articulo}}</p>
        <p>{{item.cantidad}}</p>
        <p>{{item.valor}}</p>
        <p>{{item.total}}</p>
      </div>
    </div>
  </div>
</template>

