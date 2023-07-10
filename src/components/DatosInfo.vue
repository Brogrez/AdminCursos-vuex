<template>
  <div class="container">
    <div class="centrar permitidos">
      <b-icon font-scale="2" style="color: #6a1b9a" icon="people-fill"></b-icon>
      <p style="color: #6a1b9a">Cantidad total de alumnos permitidos:<span class="font-weight-bold ml-1">{{AlumnosPermitidos}}</span> cursos</p>
    </div>
    <div class="centrar inscritos" >
      <b-icon font-scale="2" style="color: #42a5f5" icon="person-check-fill"></b-icon>
      <p style="color: #42a5f5">Cantidad total de alumnos inscritos: <span class="font-weight-bold ml-1">{{alumnosInscritos}}</span> cursos</p>
    </div>
    <div class="centrar restantes">
      <b-icon font-scale="2" style="color: #e53935"  icon="person-plus-fill"></b-icon>
      <p style="color: #e53935" >Cantidad total de cupos restantes:<span class="font-weight-bold ml-1">{{alumnosRestantes}}</span> cursos</p>
    </div>
    <div class="centrar terminados">
      <b-icon font-scale="2" style="color: #da2969" icon="lock-fill"></b-icon>
      <p style="color: #da2969">Cantidad total de cursos terminados:<span class="font-weight-bold ml-1">{{cursosTerminados}}</span> cursos</p>
    </div>
    <div class="centrar activos">
      <b-icon font-scale="2" style="color: #00c853" icon="unlock-fill"></b-icon>
      <p style="color: #00c853">Cantidad total de cursos activos:<span class="font-weight-bold ml-1">{{cursosActivos}}</span> cursos</p>
    </div>
    <div class="centrar total-cursos">
      <b-icon font-scale="2" style="color: #f57f17" icon="journal-bookmark-fill"></b-icon>
      <p style="color: #f57f17">Cantidad total de cursos:<span class="font-weight-bold ml-1">{{conteoCursos}}</span> cursos</p>
    </div>
  </div>
</template>

<script>
import {mapGetters} from 'vuex'
export default {
    name:'info-basica',
    computed:{
         ...mapGetters (['conteoCursos', 'cursosActivos', 'cursosTerminados', 'alumnosInscritos', 'AlumnosPermitidos','alumnosRestantes'])
    }
};
</script>

<style scoped>
.centrar {
  display: flex;
  align-items: center;
  margin: 1rem;
  padding: 0.5rem;
  border-radius: 0.5rem;
}
p {
  margin: 0;
  margin-left: 1rem;
}

.permitidos {
  border: 2px solid #6a1b9a;
}
.inscritos{
    border:2px solid #42a5f5;
}
.restantes{
     border:2px solid #e53935;
}
.terminados{
    border: 2px solid #da2969;
}
.activos{
    border:2px solid #00c853;
}
.total-cursos{
    border: 2px solid #f57f17;
}
</style>
