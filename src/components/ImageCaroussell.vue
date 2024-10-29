<script lang="ts" setup>
import productOne from '@/assets/image-product-1.jpg'
import productTwo from '@/assets/image-product-2.jpg'
import productThree from '@/assets/image-product-3.jpg'
import productFour from '@/assets/image-product-4.jpg'
import productOneThumbnail from '@/assets/image-product-1-thumbnail.jpg'
import productTwoThumbnail from '@/assets/image-product-2-thumbnail.jpg'
import productThreeThumbnail from '@/assets/image-product-3-thumbnail.jpg'
import productFourThumbnail from '@/assets/image-product-4-thumbnail.jpg'

import { ref } from 'vue'
import ImageButton from './ImageButton.vue'

const selectedImage = ref(productOne)

// eslint-disable-next-line @typescript-eslint/no-explicit-any
const swapImage = (image: any) => {
  selectedImage.value = image
}
</script>

<template>
  <div class="flex flex-col items-center justify-center">
    <div class="flex items-center justify-center">
      <img class="w-[70%] h-auto rounded-lg" v-bind:src="selectedImage" />
    </div>
    <div class="flex w-[70%] justify-between pt-4">

      <ImageButton :action="swapImage" :image="productOne" :thumbnail="productOneThumbnail" :selectedImage="selectedImage"/>

      <ImageButton :action="swapImage" :image="productTwo" :thumbnail="productTwoThumbnail" :selectedImage="selectedImage"/>

      <ImageButton :action="swapImage" :image="productThree" :thumbnail="productThreeThumbnail" :selectedImage="selectedImage"/>

      <ImageButton :action="swapImage" :image="productFour" :thumbnail="productFourThumbnail" :selectedImage="selectedImage"/>

    </div>
  </div>
</template>
