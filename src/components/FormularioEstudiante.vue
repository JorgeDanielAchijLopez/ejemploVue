<script setup>
import { ref } from 'vue'

const nombre = ref('')
const carrera = ref('')

const emit = defineEmits(['agregar'])

function agregarEstudiante() {
  if (nombre.value === '' || carrera.value === '') {
    return
  }

  emit('agregar', {
    nombre: nombre.value,
    carrera: carrera.value
  })

  nombre.value = ''
  carrera.value = ''
}
</script>

<template>
  <div class="formulario">
    <h2>Agregar estudiante</h2>

    <input
      v-model="nombre"
      type="text"
      placeholder="Nombre del estudiante"
    />

    <input
      v-model="carrera"
      type="text"
      placeholder="Carrera"
    />

    <button @click="agregarEstudiante">
      Agregar estudiante
    </button>
  </div>
</template>