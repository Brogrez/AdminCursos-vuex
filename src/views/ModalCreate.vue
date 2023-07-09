<template>
  <div>
    <b-button v-b-modal.modal1>Agregar Curso</b-button>

    <b-modal ref="my-modal" id="modal1" hide-footer>
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
        <b-form-group id="input-group-1" label="Nombre" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="curso.nombre"
            type="text"
            placeholder="introduzca el nombre"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="input-group-1"
          label="URL de la imagen"
          label-for="input-2"
        >
          <b-form-input
            id="input-2"
            v-model="curso.img"
            type="text"
            placeholder="URL"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-1" label="Cupos" label-for="input-3">
          <b-form-input
            id="input-3"
            v-model="curso.cupos"
            type="number"
            placeholder="Cupos del curso"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-1" label="Inscritos" label-for="input-4">
          <b-form-input
            id="input-4"
            v-model="curso.inscritos"
            type="number"
            placeholder="inscritos en el curso"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="input-group-1"
          label="duracion del curso"
          label-for="input-5"
        >
          <b-form-input
            id="input-5"
            v-model="curso.duracion"
            type="text"
            placeholder="duracion"
            required
          ></b-form-input>
        </b-form-group>

        <div>
          <label for="example-datepicker">Fecha</label>
          <b-form-datepicker
            id="example-datepicker"
            v-model="curso.fecha_registro"
            class="mb-2"
          ></b-form-datepicker>
        </div>

        <b-form-group id="input-group-1" label="Costo" label-for="input-4">
          <b-form-input
            id="input-4"
            v-model="curso.costo"
            type="number"
            placeholder="costo del curso"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group label="Descripcion">
          <b-form-textarea
            id="textarea"
            v-model="curso.descripcion"
            placeholder="ingrese una descripcion del curso"
            rows="3"
            max-rows="6"
          ></b-form-textarea>

          <pre class="mt-3 mb-0">{{ text }}</pre>
        </b-form-group>

        <b-button type="submit" variant="primary">Submit</b-button>
        <b-button type="reset" variant="danger">Reset</b-button>
      </b-form>
    </b-modal>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "ModalCreate",
  data() {
    return {
      curso: {
        id: null,
        nombre: "",
        img: "",
        cupos: null,
        inscritos: null,
        duracion: "",
        fecha_registro: "",
        costo: null,
        descripcion: "",
      },
      show: true,
    };
  },
  methods: {
    ...mapActions(["add_curso"]),

    onSubmit(event) {
      event.preventDefault();
      this.curso.id = Date.now();
      this.add_curso(this.curso);
      console.log(this.curso);
      this.$refs["my-modal"].hide();
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.curso.nombre = "";
      this.curso.img = "";
      this.curso.cupos = null;
      this.curso.inscritos = null;
      this.curso.duracion = "";
      this.curso.fecha_registro = null;
      this.curso.costo = null;
      this.curso.descripcion = "";
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>

<style></style>
