<template>
  <div>
    <label for="">Tarea</label>
    <input type="text" placeholder="Ingresa tarea" v-model="nuevaActividad" />
    <button @click="agregarNuevaActividad">Agregar</button>
  </div>
</template>

<script>
export default {
  name: "ToDoAdd",
  data: () => ({
    nuevaActividad: "",
  }),
  methods: {
    agregarNuevaActividad() {
      //   recibir dos arguemntos. 1ro Nombre del argumento. 2do info para pasar hacia afuer
      this.$emit("nueva-actividad", this.nuevaActividad);
      this.nuevaActividad = "";
    },
  },
};
</script>

<style></style>
