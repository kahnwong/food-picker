<template>
  <q-page class="row items-center justify-evenly q-pt-lg">
    <food-component title="Example component" active :menus="menus"></food-component>
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import FoodComponent from 'components/FoodComponent.vue'

const menus = ref<string[]>([
  'ข้าวอบหม้อดิน',
  'ผัดไทย',
  'ราดหน้า',
  'สุกี้',
  'หมี่สามย่าน',
  'หมี่โอเดียน',
  'หอยทอด',
  'เตี๋ยวเป็ด',
  'เย็นตาโฟ',
  'แสนยอด',
])
</script>
