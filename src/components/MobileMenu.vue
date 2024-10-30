<script lang="ts" setup>
import { defineProps } from 'vue'
import closeIcon from '@/assets/icon-close.svg'

//import type { Ref } from 'vue';

defineProps<{
  toggleMenu: () => void
  isVisible: boolean
}>()
</script>

<template>
  <div
      v-if="isVisible"
      class="fixed z-30  inset-0 flex items-center justify-center bg-black bg-opacity-80"
    >
    <div
    v-if="isVisible"
    class="absolute z-30 top-full  bg-white w-[200%]  drop-shadow-2xl"
    >
    <div class=" p-4">
      <div class="py-4 flex w-[70%] justify-end hover:cursor-pointer">
        <img
        class="w-4 h-auto rounded-lg hover:text-orange-400"
        v-bind:src="closeIcon"
        @click="() => toggleMenu()"
        />
      </div>
    </div>
    <div class="flex items-center justify-center w-full h-[300px]">
      <div  class="flex items-center">
        <div class="flex flex-col space-x-0">
          <a
          href="index.html"
          class="py-6 px-8 text-[color:hsl(0,0%,0%)]"
          >Collections</a
          >
          <a
          href="index.html"
          class="py-6 px-8 text-[color:hsl(0,0%,0%)]"
          >Men</a
          >
          <a
          href="index.html"
          class="py-6 px-8 text-[color:hsl(0,0%,0%)] "
          >Women</a
          >
          <a
          href="index.html"
          class="py-6 px-8 text-[color:hsl(0,0%,0%)]"
          >About</a
          >
          <a
          href="index.html"
          class="py-6 px-8 text-[color:hsl(0,0%,0%)]"
            >Contact</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
  </template>

<style scoped>
.absolute {
  left: -30%;
  top: 66%;
}

@media (max-width: 768px) {
  .absolute {
    top: 0%;
    width: 50%;
    height: 100%;
    left: -0%;
  transform: translateX(0%);
  }
}

</style>
