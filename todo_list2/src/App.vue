<template>
  <div id="app">
    <div class="container">
      <h1>Crea una Tarea</h1>
      <form v-on:submit.prevent="ingresarTarea">
        <p>Tarea: <input type="text" v-model="nombre" /></p>
        <button type="submit">Ingresar Tarea</button>
      </form>
        <h2>Lista de Tareas</h2>
       <HelloWorld :tareas="this.tareas" @deleteItem="deleteItem" />
     
    </div> 
  
  </div>
 
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue"
export default {
  name: "App",
  components: {
    HelloWorld,
  },
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
    deleteItem: function(index){
        this.tareas.splice(index,1)
    }
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


