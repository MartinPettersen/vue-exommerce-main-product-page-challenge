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
  <Teleport to="body">
    <div v-if="isVisible" class="fixed bg-pink-200">
      <div class="border-b-2">
        <h3>Cart</h3>
      </div>
      <div>
        <p>Your Cart is Empty</p>
      </div>
    </div>
  </Teleport>
</template>
