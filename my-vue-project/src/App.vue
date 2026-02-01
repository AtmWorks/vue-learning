<script setup lang="ts">
import { ref, type Ref } from "vue";

//lesson 1: reactive variables

const myId = "patata";
const refNumber: Ref<number> = ref(0);
const inputValue: Ref<string> = ref("v-model value");

const addUntil10 = () => {
  refNumber.value++;
  if (refNumber.value > 10) {
    refNumber.value = 0;
  }
};

setInterval(() => {
  addUntil10();
}, 1000);

//lesson 2: dinamic classes
let classDefiner = true;
setInterval(() => {
  classDefiner = !classDefiner;
}, 2000);

//lesson 3: v-for lists
const renderList: Array<string> = ["item 1", "item 2", "item 3", "item 4"];

//lesson 4: v-for objectos
const animals: Array<{ name: string; id: number; image: string }> = [
  {
    name: "dog",
    id: 1,
    image:
      "https://img.freepik.com/foto-gratis/perro-pug-aislado-sobre-fondo-blanco_2829-11416.jpg?semt=ais_hybrid&w=740&q=80",
  },
  {
    name: "gato",
    id: 2,
    image:
      "https://media.istockphoto.com/id/1443562748/es/foto/lindo-gato-de-jengibre.jpg?s=612x612&w=0&k=20&c=JVC5Z3LxpaTQaXu_fMZjIb73r39z6b0SnAxvNI8iZG0=",
  },
  {
    name: "hamster",
    id: 3,
    image:
      "https://www.zooplus.es/magazine/wp-content/uploads/2018/08/s%C3%BC%C3%9F-hamster.webp",
  },
];
</script>

<template>
  <!-- <h1 v-bind:id="myId" :class="classDefiner ? 'title' : 'other-title'"> -->
  <h1
    v-bind:id="myId"
    :class="{ title: classDefiner, 'other-title': !classDefiner }"
  >
    Hola!
  </h1>
  <div class="list-item-box">
    <p
      v-for="(listItem, index) in renderList"
      :key="index"
      :class="{ title: index % 2 === 0, 'other-title': index % 2 !== 0 }"
    >
      {{ index + 1 + "-" + listItem }}
    </p>
  </div>
  <h2 @click="addUntil10">{{ refNumber }}</h2>
  <input type="text" v-model="inputValue" class="inputTextVmoldel" />
  <div class="animals">
    <div v-for="animal in animals" :key="animal.id">
      <h3>{{ animal.name }}</h3>
      <img :src="animal.image" :alt="animal.name" width="200" height="200" />
    </div>
  </div>
</template>

<style scoped>
.title {
  color: #42b983;
}
.other-title {
  color: #b84283;
}
.animals {
  display: flex;
  flex-direction: row;
  gap: 20px;
}
.list-item-box {
  /* widht should be as big as the size determined by the items inside */
  width: fit-content;
  padding-right: 50px;
  padding-left: 50px;
  border:
    1px,
    solid #72ce78;
  display: flex;
  flex-direction: row;
  gap: 30px;
  justify-content: center;
  margin: 0 auto;
}
.inputTextVmoldel {
  height: 25px;
  width: 200px;
  padding: 10px;
  padding-left: 5%;
  /* rounded corners, all corners */
  border-radius: 50px;
  border: 2px solid #72ce78;
  /* when clicked or focus, change to yellow and back to normal size*/
}
.inputTextVmoldel:focus,
.inputTextVmoldel:hover {
  border: 2px solid #b84283;
  transform: scale(1.05);
  outline: none;
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
