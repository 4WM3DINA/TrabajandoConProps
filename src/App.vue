<template>
  <div id="app">
    <h1>Listado de tareas</h1>
    <hr />
    <img
      alt="Tareas"
      width="300px"
      height="300px"
      src="../src/assets/TAREAS.jpg"
    />
    <ChildrenComponent
      :tareas="tareas"
      @enviarTarea="agregarTarea"
      @quitarTarea="eliminarTarea"
    />
  </div>
</template>

<script>
import ChildrenComponent from "./components/ChildrenComponent.vue";

export default {
  name: "App",
  components: {
    ChildrenComponent,
  },
  data() {
    return {
      tareas: [],
    };
  },
  methods: {
    agregarTarea(task) {
      this.tareas.push(task);
    },
    eliminarTarea(i) {
      this.tareas.splice(i, 1);
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
  color: #25257c;
  font-size: 20px;
  font-weight: bold;
  background-image: url("https://img.freepik.com/vector-gratis/borde-disenos-florales-flores-rosadas_1305-5301.jpg?w=2000");
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
