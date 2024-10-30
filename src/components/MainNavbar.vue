<script lang="ts" setup>
import logo from '@/assets/logo.svg'
import menu from '@/assets/icon-menu.svg'
import cart from '@/assets/icon-cart.svg'
import avatar from '@/assets/image-avatar.png'
import { defineProps } from 'vue'
import CartDropDownMenu from './CartDropDownMenu.vue'

import { ref, onMounted, onUnmounted } from 'vue'

defineProps<{
  isVisible: boolean;
  toggleCart: () => void;
  shoppingCart: number;
  deleteProduct: () => void
}>()

const isMobile = ref(window.innerWidth < 768)

const updateIsMobile = () => {
  isMobile.value = window.innerWidth < 768
}

onMounted(() => {
  window.addEventListener('resize', updateIsMobile)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateIsMobile)
})

</script>

<template>
  <div class="flex items-center justify-center  ">

    <nav
    class="flex  flex-row justify-between border-b-2 border-[color:hsl(223, 64%, 98%)]"
    >
    <div class="flex flex-row">

      <img v-if="isMobile" class="h-4 w-auto m-6" v-bind:src="menu" />


      <img class="h-4 md:h-10 w-auto mt-6 md:mt-12" v-bind:src="logo" />

      <div v-if="!isMobile" class="flex items-center">
        <div class="flex space-x-0">
          <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"
          >Collections</a
          >
          <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"
          >Men</a
          >
          <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)] border-b-4 border-[color:hsl(26,100%,55%)]"
          >Women</a
          >
          <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"
          >About</a
          >
          <a
            href="index.html"
            class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"
            >Contact</a
            >
          </div>
        </div>
      </div>

      <div class="flex px-8 flex-row items-center relative">
        <button @click="toggleCart()">
          <img  class="h-4 w-auto m-4 " v-bind:src="cart" />
        </button>
        <CartDropDownMenu :deleteProduct="deleteProduct" :isVisible="isVisible" :shoppingCart="shoppingCart"/>

        <img class="h-6 md:h-12 w-auto " v-bind:src="avatar" />
      </div>
    </nav>
  </div>
</template>
