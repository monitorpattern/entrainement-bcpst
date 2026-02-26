<script setup lang="ts">
import { ref, onMounted } from 'vue';

const message = ref("Chargement....");

onMounted(async () => {
  try {
    const response = await fetch("http://localhost:8000/");
    const data = await response.json();
    message.value = data.message;
    console.log("Réponse reçue du backend:", response);
    console.log("Message reçu du backend:", message.value);
  } catch (error) {
    console.error("Problème de chargement de la page xxx", error);
    message.value = "Echec du chargement de la page xxx.";
  }
});
</script>

<template>
  <h1>You did it! Vue + FastAPI</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
</template>

<style scoped></style>
