<template>

  <body>
    <AppHeader></AppHeader>
    <AppText></AppText>
  </body>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AppHeader from './components/Header.vue';
import AppText from './components/TextBox.vue';

export default defineComponent({
  name: 'App',
  components: {
    AppHeader,
    AppText
  }
});
</script>

<style>
body {
  background-color: #ECECEC;
  font-family: 'Poppins', sans-serif;
  width: 100%;
  height: 100vh;
}
</style>
