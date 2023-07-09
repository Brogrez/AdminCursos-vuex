<template>
  <div class='container'>
    <table class="bordes tabla">
        <tr class="bordes">
            <th class="px-4">Cursos</th>
            <th class="px-4">Cupos</th>
            <th class="px-4">Inscritos</th>
            <th class="px-4">Duracion</th>
            <th class="px-4">Costo</th>
            <th class="px-4">Terminado</th>
            <th class="px-4">Fecha</th>
            <th class="px-4">Acciones</th>
        </tr>
        <tr class="bordes" v-for="curso in cursos" :key='curso.id'>
            <td class="px-4 font-weight-bold">{{curso.nombre}}</td>
            <td class="px-4">{{curso.cupos}}</td>
            <td class="px-4">{{curso.inscritos}}</td>
            <td class="px-4">{{curso.duracion}}</td>
            <td class="px-4"> <span class="span">${{curso.costo}}</span></td>
            <td class="px-4"><b-badge class="p-3" pill :variant="curso.completado ? 'primary' : 'secondary'">{{curso.completado ? 'Si' : 'No'}} </b-badge></td>
            <td class="py-4"><span class="span">{{curso.fecha_registro}}</span></td>
            <td class="px-4">
                <button class="btn"><b-icon icon="pencil-fill" variant='warning'></b-icon></button>
                <button class="btn"><b-icon icon="trash-fill" variant='danger'></b-icon></button>
            </td>
        </tr>
    </table>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
name:'Tabla-Cursos',
 computed: {
    ...mapState(["cursos"]),
  },
  methods:{
  
  }
}
</script>

<style scoped>
.tabla{
    margin:5rem auto;
    margin-top: 1rem ;
}
.bordes{
    border:1px solid black;
}
.btn:hover{
    background-color: #8443ac;
}
.span{
    padding: 0.5rem;
    border-radius: 1rem;
    background-color: #00c853;
    color: white;
}

</style>