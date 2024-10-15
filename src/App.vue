<script setup lang="ts">
import { ref } from "vue";
import NavBar from "./components/NavBar.vue";

const activeId = ref(3);
</script>

<template>
  <main>
    <NavBar :activeId="activeId" @setActive="activeId = $event" />
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
