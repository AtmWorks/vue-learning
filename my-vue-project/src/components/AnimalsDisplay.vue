<script setup lang="ts">

defineProps({
    animals: Array<{ name: string; id: number; image: string }>
})
//lesson 4: v-for objectos
// const animals: Array<{ name: string; id: number; image: string }> = [
//   {
//     name: "dog",
//     id: 1,
//     image:
//       "https://img.freepik.com/foto-gratis/perro-pug-aislado-sobre-fondo-blanco_2829-11416.jpg?semt=ais_hybrid&w=740&q=80",
//   },
//   {
//     name: "cat",
//     id: 2,
//     image:
//       "https://media.istockphoto.com/id/1443562748/es/foto/lindo-gato-de-jengibre.jpg?s=612x612&w=0&k=20&c=JVC5Z3LxpaTQaXu_fMZjIb73r39z6b0SnAxvNI8iZG0=",
//   },
//   {
//     name: "hamster",
//     id: 3,
//     image:
//       "https://www.zooplus.es/magazine/wp-content/uploads/2018/08/s%C3%BC%C3%9F-hamster.webp",
//   },
// ];
</script>

<template>
  <div class="animals">
    <div v-for="animal in animals" :key="animal.id">
      <h3>{{ animal.name }}</h3>
      <img :src="animal.image" :alt="animal.name" width="200" height="200" />
    </div>
  </div>
</template>

<style scoped>
.animals {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 20px;
}
.animals img {
  border-radius: 15px;
  border: 5px solid #72ce78;
}
.animals img:hover {
  border: 5px solid #b84283;
  transform: scale(1.05);
}
</style>
