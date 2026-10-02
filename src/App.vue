<script setup>
import { ref } from 'vue'

import FormularioEstudiante from './components/FormularioEstudiante.vue'
import EstudianteCard from './components/EstudianteCard.vue'

const estudiantes = ref([])

function agregarEstudiante(nuevoEstudiante) {
  estudiantes.value.push(nuevoEstudiante)
}
</script>

<template>
  <main>
    <h1>Registro de estudiantes</h1>

    <FormularioEstudiante
      @agregar="agregarEstudiante"
    />

    <h2>Estudiantes registrados</h2>

    <div class="lista">
      <EstudianteCard
        v-for="(estudiante, index) in estudiantes"
        :key="index"
        :nombre="estudiante.nombre"
        :carrera="estudiante.carrera"
      />
    </div>
  </main>
</template>

<style scoped>
main {
  max-width: 700px;
  margin: 40px auto;
  font-family: Arial, sans-serif;
}

h1 {
  text-align: center;
}

.formulario {
  margin-bottom: 30px;
}

.lista {
  display: grid;
  gap: 15px;
}
</style>