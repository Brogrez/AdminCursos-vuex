<template>
  <div>
    <b-navbar toggleable="lg" type="dark" class="colorNav">
      <b-navbar-brand href="#">NavBar</b-navbar-brand>

      <router-link to="/">
        <button class="btn">
          <b-icon class="mx-1 mt-1 icono" font-scale="1.5" icon="house-fill"></b-icon>
        </button>
      </router-link>
      <router-link to="/administracion">
        <button class="btn">
          <b-icon class="mx-1 mt-1 icono" font-scale="1.5" icon="gear-wide"></b-icon>
        </button>
      </router-link>
    </b-navbar>

  </div>
</template>

<script>
export default {
  name: "Nav-Bar",
};
</script>

<style scoped>
.colorNav {
  background-color: #6a1b9a;
}
.btn{
  margin:0 1rem ;
}
.btn:hover{
  background: #8443ac;
}
.icono{
  color:white;
}
</style>
