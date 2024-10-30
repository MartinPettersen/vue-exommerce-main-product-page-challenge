<script lang="ts" setup>
import plus from '@/assets/icon-plus.svg'
import minus from '@/assets/icon-minus.svg'
import ImageCaroussell from './ImageCaroussell.vue';
import { defineProps } from 'vue';
  //import type { Ref } from 'vue';

  const props = defineProps<{
    productCount: number;
    plusOne: () => void;
    minusOne: () => void;
    addProduct: () => void;
  }>();


</script>

<template>
  <section class="mb-6 md:mb-0 md:py-20 flex items-center justify-center">
    <div class="flex flex-col items-center justify-center md:flex-row w-full md:w-[68%]">
      <div class="md:w-[50%] mb-4 md:mb-0">
        <ImageCaroussell />
      </div>

      <div class="w-[50%] flex flex-col space-y-4">
        <h3 class="text-[color:hsl(219,9%,45%)]">SNEAKER COMPANY</h3>

        <h1 class="font-extrabold text-4xl">Fall Limited Edition Sneaker</h1>
        <p class="text-[color:hsl(219,9%,45%)]">
          These low-profile sneakers are your perfect casual wear companion.
          Featuring a durable outer sole, they'll withstand everything the
          weather can offer
        </p>
        <div class="flex flex-row space-x-2">
          <p class="font-extrabold text-lg">$125.00</p>
          <p
            class="bg-black text-white flex items-center justify-center px-1 rounded-md"
          >
            50%
          </p>
        </div>
        <p class="text-[color:hsl(219,9%,45%)] line-through">$250.00</p>
        <div class="flex flex-row space-x-2 ">
          <div
            class="flex flex-row items-center justify-center px-3 rounded-md space-x-4 bg-[color:hsl(223,64%,98%)]"
          >
            <button @click="props.minusOne()" class="py-4 px-2">
              <img class="h-1 w-auto hover:cursor-pointer" v-bind:src="minus" />
            </button>

            <p>{{ props.productCount }}</p>
            <button @click="props.plusOne()" class="py-4 px-2">
              <img class="h-3 w-auto hover:cursor-pointer" v-bind:src="plus" />
            </button>
          </div>
          <button @click="props.addProduct()"
            class="bg-[color:hsl(26,100%,55%)] flex-grow hover:bg-[color:hsl(25,100%,94%)] rounded-md"
          >
            Add to Cart
          </button>
        </div>
      </div>
    </div>
  </section>
</template>
