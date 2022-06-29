<template>
  <div class="hijo">
    <div class="contenedor">
      <form @submit.prevent="enviarTarea(tarea)">
        Tarea
        <input
          type="text"
          placeholder="ingresa nueva tarea"
          v-model="tarea"
          class="place"
        />
        <button type="submit" class="button">Añade</button>
      </form>
      <ul class="lista">
        <li v-for="(valor, index) in tareas" :key="index">
          {{ valor }}
          <button @click.prevent="quitarTarea(index)">Eliminar</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChildrenComponent",
  props: {
    tareas: {
      type: Array,
    },
  },
  data() {
    return {
      tarea: "",
    };
  },
  methods: {
    enviarTarea(tarea) {
      if (tarea) {
        this.$emit("enviarTarea", tarea);
        this.tarea = "";
      }
    },
    quitarTarea(i) {
      this.$emit("quitarTarea", i);
    },
  },
};
</script>

<style scoped>
body {
  margin: 0;
  padding: 0;
}
.hijo {
  text-align: center;
}
.lista {
  text-align: left;
  margin-left: 40vw;
}
.button {
  background-color: rgb(243, 207, 45);
  border: 3px solid rgb(8, 8, 8);
  margin: 0.4rem;
}
.place {
  background-color: rgb(233, 145, 214);
  border: 3px solid rgb(8, 8, 8);
  font-weight: bold;
}
</style>
