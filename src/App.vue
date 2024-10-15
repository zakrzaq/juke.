<script setup lang="ts">
import NavBar from "./components/NavBar.vue";
</script>

<template>
  <main>
    <NavBar />
  </main>
</template>

<style scoped>
main {
    background-color: var(--backgroud-color);
    min-height: 100vh;
    min-width: 80vw;
    margin: 0 auto;
}
</style>
