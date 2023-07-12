<template>
  <div class="container">
    <b-button @click="openCreateModal((curso = {}), 'add')" variant="primary"
      >Agregar Curso</b-button
    >
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
      <tr class="bordes" v-for="curso in cursos" :key="curso.id">
        <td class="px-4 font-weight-bold">{{ curso.nombre }}</td>
        <td class="px-4">{{ curso.cupos }}</td>
        <td class="px-4">{{ curso.inscritos }}</td>
        <td class="px-4">{{ curso.duracion }}</td>
        <td class="px-4">
          <span class="span">${{ curso.costo }}</span>
        </td>
        <td class="px-4">
          <b-badge
            class="p-3"
            pill
            :variant="curso.completado ? 'primary' : 'secondary'"
            >{{ curso.completado ? "Si" : "No" }}
          </b-badge>
        </td>
        <td class="py-4">
          <span class="span">{{ curso.fecha_registro }}</span>
        </td>
        <td class="px-4">
          <!-- <EditarCurso :id="curso.id" /> -->
          <button
            @click="openCreateModal(curso, 'edit')"
            class="btn"
            variant="primary "
          >
            <b-icon icon="pencil-fill" variant="warning"></b-icon>
          </button>

          <button class="btn" @click="confirmDelete(curso)">
            <b-icon icon="trash-fill" variant="danger"></b-icon>
          </button>
        </td>
      </tr>
    </table>
    <modal-create
      :course="currentCourse"
      :action="currentAction"
    ></modal-create>
  </div>
</template>

<script>
import { mapState } from "vuex";
import { mapActions } from "vuex";
import ModalCreate from "./ModalCreate.vue";

export default {
  name: "Tabla-Cursos",
  data() {
    return {
      currentCourse: {},
      currentAction: "",
    };
  },
  computed: {
    ...mapState(["cursos"]),
  },
  components: {
    ModalCreate,
  },
  methods: {
    ...mapActions(["eliminar_curso"]),

    openCreateModal(course, action) {
      this.currentCourse = { ...course };
      this.currentAction = action;
      this.$bvModal.show("modalCreate");
    },
    confirmDelete(curso) {
      this.$swal.fire({
        title: `Estas seguro que quieres Eliminar ${curso.nombre}?`,
        text: "Esta acción es irreversible",
        icon: "warning",
        showCancelButton: true,
        confirmButtonColor: "#3085d6",
        cancelButtonColor: "#d33",
        confirmButtonText: "Si, Eliminar!",
      }).then((result) => {
        console.log(result)
        if (result.isConfirmed) {
          this.clear(curso)
          this.$swal.fire("Eliminado!", "El curso fue eliminado.", "success");
        }
      });
      // this.$swal('Hello Vue world!!!');
    },
    clear(course) {
      console.log(course);
      this.eliminar_curso(course);
    },
  },
};
</script>

<style scoped>
.tabla {
  margin: 5rem auto;
  margin-top: 1rem;
}
.bordes {
  border: 1px solid black;
}
.btn:hover {
  background-color: #8443ac;
}
.span {
  padding: 0.5rem;
  border-radius: 1rem;
  background-color: #00c853;
  color: white;
}
</style>
