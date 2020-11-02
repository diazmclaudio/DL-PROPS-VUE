<template>
  <section class="container my-2">
    <form @submit.prevent="enviarTareas">
      <div class="form-group">
        <label for="tarea">Ingresa una tarea</label>
        <input type="text" class="form-control" v-model="tarea">
        <small id="emailHelp" class="form-text text-muted">Escribe aquí</small>
      </div>
      <div class="form-group">
        <label for="imagen">Ingresa una imagen</label>
        <input type="text" class="form-control" v-model="imagen">
        <small id="emailHelp" class="form-text text-muted">Pega un link</small>
      </div>
      <div class="form-group">
        <label for="descripcion">Ingresa una descripción de tu tarea</label>
        <input type="text" class="form-control" v-model="descripcion">
        <small id="emailHelp" class="form-text text-muted">Escribe aquí</small>
      </div>
      <button type="reset" class="btn btn-warning text-white mr-4">Borrar todo</button>
      <button type="submit" class="btn btn-primary bg-info">Agregar tarea</button>
  </form>
  </section>
</template>

<script>
  export default {
    name: 'Tareas',
    data() {
      return {
        tarea: '',
        imagen: '',
        descripcion: '',
        id: 1
      }
    },
    methods: {
      enviarTareas(){
        if (this.tarea && this.imagen && this.descripcion) {
          let listaTareas = {
            tarea: this.tarea,
            imagen: this.imagen,
            descripcion: this.descripcion,
            id: this.id++
        };
        this.$emit('enviandoTareas', listaTareas);
        this.tarea = "";
        this.imagen = "";
        this.descripcion = "";
        }
        else {
          console.log("No hay datos");
        }
      }  
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form {
  width: 50%;
  margin-left: 50px;
  margin-top: 50px;
}
</style>