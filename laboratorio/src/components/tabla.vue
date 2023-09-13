<script lang="ts">
import { defineComponent } from 'vue';
import Item from './Item.vue';

export default defineComponent({
    props: {
        datos: {
            type: Array<object>,
            required: true,
        }
    },
    components: {
        Item
    }
})
</script>

<template>
    <div>
    <div class="item">
        <p>id</p>
        <p>articulo</p>
        <p>cantidad</p>
        <p>valor</p>
        <p>total</p>
    </div>
    <div v-for="datosItem in datos" class="item">
        <Item :datosItem="datosItem" />
    </div>
</div>
</template>
    
