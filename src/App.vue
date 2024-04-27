<template>

  <body>
    <AppHeader></AppHeader>
    <AppNavbar></AppNavbar> 
    <AppStacks></AppStacks>
  </body>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AppHeader from './components/Header.vue';
import AppStacks from './components/StackBox.vue';
import AppNavbar from './components/Navbar.vue';

export default defineComponent({
  name: 'App',
  components: {
    AppHeader,
    AppStacks,
    AppNavbar
  }
});
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

body {
  background-color: #ECECEC;
  font-family: 'Poppins', sans-serif;
  width: 100%;
  height: 100vh;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
