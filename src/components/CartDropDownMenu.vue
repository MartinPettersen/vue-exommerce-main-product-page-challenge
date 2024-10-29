<script lang="ts" setup>
import { defineProps } from 'vue'
//import type { Ref } from 'vue';

defineProps<{
  productCount: number
  isVisible: boolean
  //plusOne: () => void
  //minusOne: () => void
}>()
</script>

<template>
    <div v-if="isVisible" class="absolute top-full mt-1 bg-white w-[200%] drop-shadow-2xl">
      <div class="border-b-2 p-4">
        <h3 class="font-bold">Cart</h3>
      </div>
      <div class="flex items-center justify-center w-full h-[300px]">
        <p class="font-bold text-[color:hsl(219,9%,45%)]">Your Cart is Empty</p>
      </div>
    </div>
</template>

<style scoped>
.absolute {
  left: -30%;
  top: 66%;
}
</style>
