<script setup lang="ts">
import Grid from './components/Grid.vue'
</script>

<template>
  <div class="top-section">
    <h1>Top Section</h1>
  </div>
  <div class="middle-section">
    <Grid />
  </div>
  <div class="bottom-section">
    <h3>Bottom Section</h3>
  </div>
</template>

<style>
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  margin: 0;
}

.top-section {
  flex: 0 0 10%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.middle-section {
  flex: 0 0 80%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.bottom-section {
  flex: 0 0 10%;
  display: flex;
  justify-content: center;
  align-items: center;
}

div,p,h1,h2,h3 {
  font-family: "Space Mono", monospace;
  font-weight: 700;
  font-style: normal;
}
</style>
