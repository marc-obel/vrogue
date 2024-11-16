<script setup lang="ts">
import { ref, computed } from 'vue'
import Cell from './Cell.vue'


type Cell = {
  row: number;
  column: number;
  type: string;
  content?: string;
};

const rows = 30;
const columns = 20;

const grid = ref<Array<Cell[]>>(
  Array.from({ length: rows }, (_, row) =>
    Array.from({ length: columns }, (_, column) => ({ row, column, type: 'floor' }))
  )
);

const flattenedGrid = computed(() => grid.value.flat());

</script>

<template>
  <div class="grid">
    <Cell
      v-for="(cell, index) in flattenedGrid"
      :key="index"
      :row="cell.row"
      :column="cell.column"
      :type="cell.type"
    />
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-rows: repeat(30, 1fr);
  grid-template-columns: repeat(20, 1fr); 
  width: 100%;
  height: 100%;
}

.grid > * {
  width: 100%;
  height: 100%;
}
</style>
