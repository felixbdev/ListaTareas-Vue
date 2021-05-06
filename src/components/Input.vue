<template>
  <input 
    type="text"
    placeholder="Nombre Tarea"
    class="form-control my-2"
    v-model.trim="tarea.nombre"
  >
  <div class="form-check form-check-inline">
    <input 
      type="checkbox" 
      class="form-check-input"
      id="check-1"
      v-model="tarea.categorias"
      value="javascript"
    >
    <label for="check-1" class="form-check-label">Javascript</label>
  </div>

  <div class="form-check form-check-inline">
    <input 
      type="checkbox" 
      class="form-check-input"
      id="check-2"
      v-model="tarea.categorias"
      value="node js"
    >
    <label for="check-2" class="form-check-label">Node JS</label>
  </div>

  <div class="mt-2">
    <div class="form-check form-check-inline">
      <input
        type="radio" 
        id="radio-1"
        class="form-check-input"
        value="urgente"
        v-model="tarea.estado"
      >
      <label for="radio-1" class="form-check-label">Urgente</label>
    </div>
    <div class="form-check form-check-inline mt-2">
      <input
        type="radio" 
        id="radio-2"
        class="form-check-input"
        value="relax"
        v-model="tarea.estado"
      >
      <label for="radio-2" class="form-check-label">Relax</label>
    </div>

    <div class="mt-2">
      <input 
      type="number"
      class="form-control mb-4"
      v-model.number="tarea.numero"
      >
    </div>
  </div>

  <button 
  class="btn btn-dark btn-block" 
  type="submit" 
  :disabled=bloquear
  >
    Procesar
  </button>
</template>

<script>
export default {
  name: 'Input',
  props: {
    tarea: Object
  },
  computed: {
    bloquear(){
      return this.tarea.nombre.trim() === "" ? true : false
    }
  }
}
</script>

<style>

</style>