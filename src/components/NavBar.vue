<template>
  <div>
    <b-navbar type="warning" class="p-2 colorNav">
      <b-navbar-nav class="row justify-content-end w-100 mx-auto">
        <b-nav-item href="#" class="item px-3">
          <router-link class="linkColor" to="/">
            <b-icon font-scale="1.5" icon="house-door-fill"></b-icon>
          </router-link>
        </b-nav-item>
        <b-nav-item href="#" class="item px-3">
          <router-link class="linkColor" to="/Administracion">
            <b-icon font-scale="1.5" icon="Gear-fill"></b-icon>
          </router-link>
        </b-nav-item>


      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Nav-Bar",
};
</script>

<style scope>
.item:hover {
  background-color: #8443ac;
  border-radius: 10px;
  margin-left: 2rem;
}
.item {
  border-radius: 10px;
  margin-left: 2rem;
}
.icono {
  text-decoration: none;
}
.colorNav {
  background-color: #6a1b9a;
}
.linkColor {
  color: white;
}

.linkColor:hover {
  color: white;
}
</style>
