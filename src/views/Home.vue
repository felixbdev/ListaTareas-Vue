<template>
  <form class="mt-3" @submit.prevent="procesarFormulario">
    
    <Input :tarea= 'tarea'/>
  </form>
  <div class="mt-4">
    <ListaTarea/>
  </div>
</template>

<script>
import Input from "../components/Input"
import {mapActions} from 'vuex'
import ListaTarea from "../components/ListaTarea"
const shortid = require('shortid')



export default {
  name: 'Home',
  components:{
    Input, ListaTarea
  },
  data() {
    return {
      tarea: {
        id: '',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }
    }
  },
  methods:{
    ...mapActions(['setTareas']),
    procesarFormulario()
    {
      console.log(this.tarea)
      if(this.tarea.nombre.trim() === "") {
        console.log('Campo Vacio')
        return
      }

      //Generar id
      this.tarea.id = shortid.generate()
      //console.log(this.tarea.id)
      this.setTareas(this.tarea)

//Limpiar datos
      this.tarea =  {
        id: '',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }
    },
  },
}

</script>
