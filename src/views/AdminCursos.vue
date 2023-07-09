<template>
  <div>
    <h1>Administración</h1>
    <ModalCreate />
    <TablaCursos />
  </div>
</template>

<script>
import TablaCursos from "@/components/TablaCursos.vue";
import ModalCreate from "./ModalCreate.vue";
export default {
  name: "VistaAdmin",
  components: {
    TablaCursos,
    ModalCreate
  },
};
</script>

<style></style>
