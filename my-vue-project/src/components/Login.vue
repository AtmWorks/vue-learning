<script lang="ts" setup>
import { ref, type Ref } from 'vue';
defineProps({
    isLogged: { type: Boolean, required: true },
    requiredUserName: { type: String, required: true }
})
//constante isLogged con acceso a la variable del prop

const emit = defineEmits(["login"]);
const userName: Ref<string> = ref("user123");
const showError: Ref<boolean> = ref(false);
//nombre del evenot y datos que viajan
const login = (isLogged:boolean, requiredName: string) => {
if (isLogged) {
    userName.value = "";
    showError.value = false;
    emit("login", "");
  }
  else if (userName.value != requiredName) {
    showError.value = true;
  }
else {emit("login", userName.value); showError.value = false;}
 
};

</script>
<template>
      <div class="login-box">
    <h2>Login emiter</h2>
    <p>{{ "Required: "+requiredUserName }}</p>
    <p :class="{ textCorrect: isLogged, 'textError': showError }" >{{ "Input: "+userName }}</p>
    <input type="text" v-model="userName" :class="{ inputTextVmoldel: !showError, 'inputTextError': showError }"/>
    <button @click="login(isLogged, requiredUserName)">{{!isLogged ? "Login" : "Logout"}}</button>
  </div>
</template>
<style scoped>
.login-box {
  width: fit-content;
  /* centered horizontally */
  margin: 0 auto;
  /* sensible padding: top/right/bottom/left */
  padding: 25px 50px 25px 50px;
  border: 1px solid #b84283;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
  margin-top: 25px;
}
.login-box h2, .login-box p {
  margin: 0;
}
.inputTextVmoldel {
  height: 25px;
  width: 200px;
  padding: 10px;
  padding-left: 5%;
  border-radius: 50px;
  border: 2px solid #72ce78;
  margin: 10px 0px 10px 0px;
}
.inputTextVmoldel:focus {
  border: 2px solid #72ce9ea2;
  outline: none;
}
.inputTextError {
  height: 25px;
  width: 200px;
  padding: 10px;
  padding-left: 5%;
  border-radius: 50px;
  border: 2px solid #ff0000;
  margin: 10px 0px 10px 0px;
}
.inputTextError:focus {
  border: 2px solid #ff15007a;
  outline: none;
}
.textCorrect {
  color: #42b983;
}
.textError {
    color: #ff0000;
}
</style>