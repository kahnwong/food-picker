<template>
  <div class="container">
    <div class="food-random">
      {{ randomMenu }}
    </div>
    <div class="food-all">
      <span class="text-bold">ALL MENUS</span>
      <ul>
        <li v-for="(menu, index) in menus" :key="index">
          {{ menu }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

interface MenuProps {
  menus: string[]
}
const props = withDefaults(defineProps<MenuProps>(), {
  menus: () => [],
})

const randomMenu = computed(() => {
  const items = props.menus
  return items[Math.floor(Math.random() * items.length)]
})
</script>

<!--generated via gemini because I suck at anything ui-related-->
<style>
.container {
  display: grid;
  grid-template-rows: 1fr 2fr; /* Top row takes 1/3 height, bottom row takes 2/3 height */
  justify-content: center;
  align-items: center;
  height: 70vh; /* viewport height */
}

.food-random {
  text-align: center;
}

.food-all {
  display: flex;
  flex-direction: column;
  align-items: center;
  list-style: none;
  padding: 0;
}

.food-all li {
  margin-bottom: 10px;
}
</style>
