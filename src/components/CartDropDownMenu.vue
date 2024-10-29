<script lang="ts" setup>
import { defineProps } from 'vue'
import deleteIcon from '@/assets/icon-delete.svg'
import thumbnail from '@/assets/image-product-1-thumbnail.jpg'

//import type { Ref } from 'vue';

defineProps<{
  shoppingCart: number
  isVisible: boolean
  deleteProduct: () => void
  //minusOne: () => void
}>()
</script>

<template>
  <div
    v-if="isVisible"
    class="absolute top-full mt-1 bg-white w-[200%] drop-shadow-2xl"
  >
    <div class="border-b-2 p-4">
      <h3 class="font-bold">Cart</h3>
    </div>
    <div class="flex items-center justify-center w-full h-[300px]">
      <div v-if="shoppingCart === 0">
        <p class="font-bold text-[color:hsl(219,9%,45%)]">Your Cart is Empty</p>
      </div>
      <div v-else class="flex items-center justify-center flex-col h-full space-y-8 ">
        <div class="flex flex-row justify-between items-center">
          <img
            :class="{}"
            class="h-12 w-auto rounded-md m-2"
            v-bind:src="thumbnail"
          />

          <div class="flex flex-col">
            <p class="text-[color:hsl(219,9%,45%)]">
              Fall Limited Edition Sneakers
            </p>
            <p class="text-[color:hsl(219,9%,45%)]">
              $125.00 x {{ shoppingCart }}
              <span class="font-bold text-black"
                >${{ shoppingCart * 125.0 }}</span
              >
            </p>
          </div>
        <button @click="deleteProduct()">
          <img class="h-4 w-auto m-4" v-bind:src="deleteIcon" />
        </button>
        </div>
        <button
            class="bg-[color:hsl(26,100%,55%)] h-[16%] w-[90%] hover:bg-[color:hsl(25,100%,94%)] rounded-md"
          >
            Checkout
          </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.absolute {
  left: -30%;
  top: 66%;
}
</style>
