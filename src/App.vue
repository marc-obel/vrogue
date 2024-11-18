<script setup lang="ts">
import Grid from './components/Grid.vue'
import { useFullscreen } from '@vueuse/core'
import { onMounted } from 'vue'

const { isFullscreen, enter } = useFullscreen()

</script>

<template>
  <button v-if="!isFullscreen" @click="enter">
    GO
  </button>
  <div v-else class="container">
    <div class="top-section">
      <h1>Top Section</h1>
    </div>
    <div class="middle-section">
      <Grid />
    </div>
    <div class="bottom-section">
      <h3>Bottom Section</h3>
    </div>
  </div>
</template>

<style>
button {
  position: absolute;
  left: 45%;
  font-size: larger;
  padding: .5rem 1rem;
}
.container {
  display: flex;
  flex-direction: column;
  height: 100dvh;
  overflow: hidden;
  margin: 0;
}

.top-section {
  flex: 0 0 10%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.middle-section {
  flex: 0 0 75%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.bottom-section {
  flex: 0 0 15%;
  display: flex;
  justify-content: center;
  align-items: center;
}

div,
p,
button,
h1,
h2,
h3 {
  font-family: "Space Mono", monospace;
  font-weight: 700;
  font-style: normal;
}
</style>
