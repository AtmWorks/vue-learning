<script setup>
import { ref } from "vue";
const author = ref("Professor pickle");
const year = ref(2025);
const href = ref("https://www.google.com");
</script>

<template>
  <footer>
    Created by
    <a v-bind:href="href"
      ><span>{{ author }}</span></a
    >
    &copy; {{ year }}
  </footer>
</template>

<style scoped>
footer {
  position: fixed;
  margin: 0 auto;
  bottom: 0;
  text-align: center;
  color: #ccd6d9;
  padding-bottom: 28px;
}
footer a {
  color: white;
}

footer span {
  font-family: cursive;
}
</style>
