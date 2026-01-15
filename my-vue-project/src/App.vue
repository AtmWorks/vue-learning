<script setup lang="ts">
import { ref, type Ref } from "vue";

//lesson 1: reactive variables
const addUntil10 = () => {
  number.value++;
  if (number.value > 10) {
    number.value = 0;
  }
};
const myId = "patata";
const number: Ref<number> = ref(0);
const inputValue: Ref<string> = ref("some value");

setInterval(() => {
  addUntil10();
}, 1000);

//lesson 2: dinamic classes
let classDefiner = true;
setInterval(() => {
  classDefiner = !classDefiner;
}, 2000);
</script>

<template>
  <!-- <h1 v-bind:id="myId" :class="classDefiner ? 'title' : 'other-title'"> -->
  <h1
    v-bind:id="myId"
    :class="{ title: classDefiner, 'other-title': !classDefiner }"
  >
    Hola!
  </h1>
  <h2 @click="addUntil10">{{ number }}</h2>
  <input type="text" v-model="inputValue" />
</template>

<style scoped>
.title {
  color: #42b983;
}
.other-title {
  color: #b84283;
}
</style>
