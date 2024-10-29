<script lang="ts" setup>
  import logo from '@/assets/logo.svg'
</script>

<template>
  <nav class="flex flex-row">
    <img class="h-10 w-auto m-16" v-bind:src="logo"/>
    <div class=" flex items-center">
      <div class="flex space-x-0 ">

        <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"

        >Collections</a>
        <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"

        >Men</a>
        <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"

        >Women</a>
        <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"

        >About</a>
        <a
          href="index.html"
          class="py-16 px-8 text-[color:hsl(219,9%,45%)] hover:text-[color:hsl(0,0%,0%)]"

        >Contact</a>
      </div>

    </div>

  </nav>
</template>
