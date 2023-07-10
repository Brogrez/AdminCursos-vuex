<template>
  <div class="container">
    <div class="row">
      <div class="col-3 margen" v-for="curso in cursos" :key="curso.id">
        <b-card
          no-body
          :img-src="curso.img"
          style="max-width: 20rem ;"
          img-alt="Image"
          img-top
        >
          <template #header>
            <h4 class="m-0 font-weight-bold">{{ curso.nombre }}</h4>
          </template>
          <b-card-title>Informacion</b-card-title>
          <b-list-group flush class="text">
            <b-list-group-item class="p-1 m-0"> <span>Costo:</span> {{ curso.costo }}</b-list-group-item>
            <b-list-group-item class="p-1 m-0"> <span>Duracion:</span> {{ curso.duracion }}</b-list-group-item>
            <b-list-group-item class="p-1 m-0"> <span>cupos</span>: {{ curso.cupos }}</b-list-group-item>
            <b-list-group-item class="p-1 m-0"> <span>Fecha de Registro:</span> {{ curso.fecha_registro }}</b-list-group-item>
            <b-list-group-item class="p-1 m-0"> <span>Descripcion:</span> {{ curso.descripcion }}</b-list-group-item>
          </b-list-group>
        </b-card>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  name: "Lista-Cursos",
  computed: {
    ...mapState(["cursos"]),
  },
};
</script>

<style scoped>
.margen{
    margin: 0 auto;
    margin-right: 1rem;
    margin-top: 1rem;
    margin-bottom: 2rem;
}
.text{
    text-align: start;
}
span{
    font-weight: bold;
}

img{
  height: 15rem;
}
</style>
