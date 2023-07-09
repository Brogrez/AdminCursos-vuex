<template>
  <div>
    <h1 class="mx-auto mt-5">Lista de Cursos</h1>
    <ListaCursos/>
  </div>
</template>

<script>
import ListaCursos from '@/components/ListaCursos.vue'
export default {
  name: "cursos-views",
  components:{
    'ListaCursos': ListaCursos,
  }
};
</script>

<style></style>
