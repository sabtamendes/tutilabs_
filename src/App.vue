<template>
  <div id="app">
    <AppHeader></AppHeader>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AppHeader from './components/Header.vue';

export default defineComponent({
  name: 'App',
  components: {
    AppHeader
  }
});
</script>

<style>
#app {
  width: 100%;
  height: 100vh;
  background-color: #ECECEC;
}
</style>
