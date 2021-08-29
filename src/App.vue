<template>
  <div>
    <h1>Crear nueva Tarea</h1>

    <ToDoAdd @nueva-actividad="agregarNuevaActividad" />
    <ToDoList :actividades="actividades" @borrar-tarea="borrarTarea" />
  </div>
</template>

<script>
import ToDoAdd from "./components/ToDoAdd.vue";
import ToDoList from "./components/ToDoList.vue";
export default {
  name: "App",
  components: { ToDoAdd, ToDoList },
  data: () => ({
    actividades: [],
  }),
  methods: {
    agregarNuevaActividad(nuevaActividad) {
      this.actividades.push(nuevaActividad);
    },
    borrarTarea($index) {
      this.actividades.splice($index);
    },
  },
};
</script>

<style></style>
