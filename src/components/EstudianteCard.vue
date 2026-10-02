<script setup>
defineProps({
  nombre: String,
  carrera: String
})
</script>

<template>
  <div class="tarjeta">
    <h3>{{ nombre }}</h3>
    <p>{{ carrera }}</p>
  </div>
</template>