<script>
import Formulario from './components/formulario.vue';
import Item from './components/Item.vue';
import { ref } from 'vue';
export default {
  components: {
    Formulario,
    Item,
  },  
  methods: {
    agregarDatoATabla(nuevoDato) {
      this.$refs.Item.$emit('nuevo-dato', nuevoDato);
    },
  },
};
</script>

<template>
  <div>
    <formulario @nuevo-dato="agregarDatoATabla" />
    <Item />
  </div>
</template>


