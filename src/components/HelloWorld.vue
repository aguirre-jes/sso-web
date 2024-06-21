<script setup lang="ts">
defineProps<{
  msg: string
}>()
import KeycloakService from "../security/KeycloakService";

const userName = KeycloakService.GetUserName();
const userRoles = KeycloakService.GetUserRoles();
const accessToken = KeycloakService.GetAccesToken();
const logOut = KeycloakService.CallLogOut;
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
    <p>User Name: {{ userName }}</p>
    <p>User Roles: {{ userRoles }}</p> 
    <p>Access Token: {{ accessToken }}</p>
    <button @click="logOut">Log Out</button>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
