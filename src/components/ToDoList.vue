<template>
  <div>
    <h1>Lista</h1>
    <ul>
      <li v-for="(actividad, $index) in actividades" :key="$index">
        {{ actividad }}

        <!-- (*) Es mejor usar $index, pq de esa manera borramos el que indice. "activdad" borraaba todas las lineas que se agregaba. $index, NO -->
        <button @click="borrarTarea($index)">Elimianr</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ToDoList",
  props: {
    actividades: { type: Array, required: true },
  },
  methods: {
    borrarTarea($index) {
      // nombre (1er argumento) tiene que ser igual a como se va a llamar/referenciar en el padre. En este caso borrar-tarea y NO como se llama en el @click="borrarTarea"

      this.$emit("borrar-tarea", $index);
    },
  },
};
</script>

<style></style>
