<script setup lang="ts">
import Header from "./components/Header.vue";
</script>

<template>
  <v-app>
    <Header />
    <main class="content">
      <router-view />
    </main>
  </v-app>
</template>

<style scoped>
.content {
  margin-top: 70px;
}
</style>
