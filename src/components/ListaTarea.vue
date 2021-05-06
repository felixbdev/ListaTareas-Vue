<template>
  <table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Nombre</th>
      <th scope="col">Categoria</th>
      <th scope="col">Estado</th>
      <th scope="col">Numero</th>
      <th scope="col">Accion</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item in tareas" :key="item.id">
      <th scope="row">{{item.id}}</th>
      <td>{{item.nombre}}</td>
      <td>{{item.categorias.join(', ')}} </td>
      <td>{{item.estado}}</td>
      <td>{{item.numero}}</td>
      <td>
        <button 
        class="btn btn-danger btn-sm"
        @click="deleteTareas(item.id)"
        >
        Eliminar
        </button>
        <button class="btn btn-warning btn-sm">Editar</button>
      </td>
    </tr>
  </tbody>
</table>
</template>

<script>
import {mapState, mapActions} from 'vuex'
export default {
  computed: {
    ...mapState(['tareas'])
  },
  methods:{
    ...mapActions(['deleteTareas'])
  }
}
</script>

<style>

</style>