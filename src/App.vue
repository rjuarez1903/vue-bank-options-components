<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Title text="Amazing 2.0" />
  <Account />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Title from './components/Title.vue';
import Account from './components/Account.vue';

export default {
  name: 'App',
  components: {
    Title, Account
  }
}
</script>

<style>

:root {
    --black: #1c1c1c
}

#app {
  min-height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
