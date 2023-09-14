<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent( {
  props: {
    datosItem: {
      type: Object,
      required: true,
    }
    }
    
  });
    


</script>

<template>
      
        <p>{{datosItem.id}}</p>
        <p>{{datosItem.articulo}}</p>
        <p>{{datosItem.cantidad}}</p>
        <p>{{datosItem.vu}}</p>
        <p>{{datosItem.total}}</p>
</template>

