<template>
  <div>
    <Tareas @enviandoTareas="cardTarea"/>
    <Cards :listaTareas="datosTareas" @eliminarTarea="borrarTareas"/>
  </div>
</template>

<script>
import Tareas from './components/Tareas.vue';
import Cards from './components/Cards.vue';
export default {
  name: 'App',
  data() {
    return {
      datosTareas: []
    }
  },
  components: {
    Tareas,
    Cards
  },
  methods: {
    cardTarea(datos){
      console.log(datos);
      this.datosTareas.push(datos);
    },
     borrarTareas(index){
      this.datosTareas.splice(index,1);
    }
  },
}
</script>

<style>
</style>