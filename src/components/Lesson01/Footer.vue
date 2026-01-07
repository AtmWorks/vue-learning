<!-- script es para meter la logica (javascript) del componente  -->

<script setup>
import { ref } from "vue";
const year = ref(new Date().getFullYear());
</script>

<template>
  <footer>
    <p>&copy; {{ year }}</p>
  </footer>
</template>

<style scoped>
footer {
  position: fixed;
  bottom: 0;
  padding-bottom: 20px;
}
footer p {
  color: rgb(21, 221, 188);
}
</style>
