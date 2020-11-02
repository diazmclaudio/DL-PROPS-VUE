<template>
   <section class="container my-5">
      <section class="row">
          <section class="col-12 col-sm-12 col-md-6 col-lg-4 col-xl-4" v-for="(tareas,index) in listaTareas" :key="index">
            <div class="card">
                <img :src="tareas.imagen" class="card-img-top" :alt="tareas.id">
                <div class="card-body">
                    <h5 class="card-title">{{tareas.tarea}}</h5>
                    <p class="card-text">{{tareas.descripcion}}</p>
                    <a href="#" class="btn btn-primary bg-info" @click.prevent="eliminarTarea(index)">Eliminar</a>
                </div>
            </div>
          </section>
      </section>
  </section>
</template>

<script>
export default {
    name: 'Cards',
    props: {
        listaTareas: {
            type: Array,
            required: true
        }
    },
     methods: {
        eliminarTarea(index){
            this.$emit('eliminarTarea', index);
        }
    },   
}
</script>

<style scoped>
    img {
        max-width: 350px;
        max-height: 350px;
    }
</style>