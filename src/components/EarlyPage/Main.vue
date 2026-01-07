<script setup>
import { ref } from "vue";
const name = ref("Albert");
</script>

<template>
  <main>
    <h1>Hello, I'm {{ name }}</h1>
    <p>
      I'm about to learn Vue!
      <a href="https://vuejs.org/" target="_blank">Vue.js</a>!
    </p>
  </main>
</template>

<style scoped>
main h1 {
  display: block;
}
main a {
  color: #42b883;
}
</style>
