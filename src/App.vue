<!-- script es para meter la logica (javascript) del componente  -->

<script setup>
import { ref } from "vue";
const name = ref("Albert");
const emoji = ref("👋");
const year = ref(new Date().getFullYear());
</script>
<!-- template es para meter el HTML del componente -->
<template>
  <header>
    <span>
      {{ emoji }}
    </span>
    <main>
      <h1>Hello, I'm {{ name }}</h1>
      <p>
        I'm about to learn Vue!
        <a href="https://vuejs.org/" target="_blank">Vue.js</a>!
      </p>
    </main>
    <footer>
      <p>&copy; {{ year }}</p>
    </footer>
  </header>
</template>
<!-- style es para meter el CSS del componente -->
<style scoped>
header span {
  font-size: 3rem;
}
main h1 {
  display: block;
}
main a {
  color: #42b883;
}
footer {
  position: fixed;
  bottom: 0;
  padding-bottom: 20px;
}
footer p {
  color: rgb(21, 221, 188);
}
</style>
