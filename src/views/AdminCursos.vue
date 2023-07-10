<template>
  <div>
    <h1>Administración</h1>
    <ModalCreate />
    <TablaCursos />
    <DatosInfo />
  </div>
</template>

<script>
import TablaCursos from "@/components/TablaCursos.vue";
import ModalCreate from "./ModalCreate.vue";
import DatosInfo from "@/components/DatosInfo.vue"
export default {
  name: "VistaAdmin",
  components: {
    TablaCursos,
    ModalCreate,
    DatosInfo
  },
};
</script>

<style scoped>
h1{
  margin: 1rem;
  font-size:5rem;
}
</style>
