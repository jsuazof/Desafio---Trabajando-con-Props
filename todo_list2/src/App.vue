<template>
  <div id="app">
    <div class="container">
      <h1>Crea una Tarea</h1>
      <form v-on:submit.prevent="ingresarTarea">
        <p>Tarea: <input type="text" v-model="nombre" /></p>
        <button type="submit">Ingresar Tarea</button>
      </form>

      <ul class="list-group" v-for="(tarea, id) in tareas" :key="tarea">
        <li class="list-group-item">{{ id }} - {{ tarea.nombre }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  el: "App",
  data() {
    return {
      nombre: "",
      tareas: [],
    };
  },
  methods: {
    ingresarTarea: function () {
      this.tareas.push({
        nombre: this.nombre,
      });
      this.nombre = "";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
