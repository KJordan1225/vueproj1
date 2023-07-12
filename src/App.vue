<script setup>
  /*
    imports
  */

  import { reactive, provide } from 'vue'
  import { RouterLink, RouterView } from 'vue-router'

  /*
    user data
  */

  const userData = reactive ({
    name: 'Keith' ,
    username: 'keithjordan'
  })

  provide('userData', userData)

</script>

<template>
  <div class="userdata">
    {{ userData.name }} @{{ userData.username }}
  </div>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/about">About</RouterLink>
    <RouterLink to="/modals">Modals</RouterLink>
  </nav>
  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

.userdata {
  position: absolute;
  background-color: orange;
  padding: 5px;
  top: 0;
  right: 0;
  font-size: 12px;
}
</style>
