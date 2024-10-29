<script lang="ts" setup>
import logo from '@/assets/logo.svg'
import cart from '@/assets/icon-cart.svg'
import avatar from '@/assets/image-avatar.png'

</script>

<template>
  <div class="flex items-center justify-center  ">

    <nav
    class="flex  flex-row justify-between border-b-2 border-[color:hsl(223, 64%, 98%)]"
    >
    <div class="flex flex-row">
      <img class="h-10 w-auto mt-12" v-bind:src="logo" />
      <div class="flex items-center">
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
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"
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

      <div class="flex px-8 flex-row items-center">
        <img class="h-4 w-auto m-4 " v-bind:src="cart" />
        <img class="h-12 w-auto " v-bind:src="avatar" />
      </div>
    </nav>
  </div>
</template>
