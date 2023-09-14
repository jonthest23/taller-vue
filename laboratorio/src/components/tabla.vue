<script lang="ts">
import { defineComponent } from 'vue';
import Item from './Item.vue';

export default defineComponent({
    props: {
        datos: {
            type: Array<object>,
            required: true,
        },
        total : {
            type: Number,
            required: true,
        },
        descuento : {
            type: String,
            required: false,
        }
    },
    components: {
        Item
    }
})
</script>

<template>
<div class="contenedor">
    <div class="item">
        <p>id</p>
        <p>articulo</p>
        <p>cantidad</p>
        <p>valor unitario</p>
        <p>total</p>
    </div>
    <div v-for="datosItem in datos" class="item">
        <Item :datosItem="datosItem" />
    </div>
    <div class="item">
        <p>Total</p>
        <p></p>
        <p></p>
        <p></p>
        <p>{{total}}  ({{ descuento }})</p>
    </div>
</div>
</template>

<style scoped>
.item {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20% ;
  border: 1px solid green;
}
.contenedor {
  width: 100%;
}
</style>
    
