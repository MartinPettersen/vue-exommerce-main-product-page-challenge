<script lang="ts" setup>
import { defineProps } from 'vue'
import productOne from '@/assets/image-product-1.jpg'
import productTwo from '@/assets/image-product-2.jpg'
import productThree from '@/assets/image-product-3.jpg'
import productFour from '@/assets/image-product-4.jpg'
import productOneThumbnail from '@/assets/image-product-1-thumbnail.jpg'
import productTwoThumbnail from '@/assets/image-product-2-thumbnail.jpg'
import productThreeThumbnail from '@/assets/image-product-3-thumbnail.jpg'
import productFourThumbnail from '@/assets/image-product-4-thumbnail.jpg'
import ImageButton from './ImageButton.vue'

defineProps<{
  swapImage: (image: string) => void
  selectedImage: string
  isVisible: boolean
  toggleLightBox: () => void
}>()
</script>

<template>
  <Teleport to="body">
    <div v-if="isVisible" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-90" @click="() => toggleLightBox()">
      <div class="flex flex-col items-center justify-center w-[50%] p-4 rounded-lg" >
        <div class="flex items-center justify-center">
          <img class="w-[70%] h-auto rounded-lg " @click.stop v-bind:src="selectedImage" />
        </div>
        <div class="flex w-[70%] justify-between pt-4" @click.stop>
          <ImageButton
            :action="swapImage"
            :image="productOne"
            :thumbnail="productOneThumbnail"
            :selectedImage="selectedImage"
          />
          <ImageButton
            :action="swapImage"
            :image="productTwo"
            :thumbnail="productTwoThumbnail"
            :selectedImage="selectedImage"
          />
          <ImageButton
            :action="swapImage"
            :image="productThree"
            :thumbnail="productThreeThumbnail"
            :selectedImage="selectedImage"
          />
          <ImageButton
            :action="swapImage"
            :image="productFour"
            :thumbnail="productFourThumbnail"
            :selectedImage="selectedImage"
          />
        </div>
      </div>
    </div>
  </Teleport>
</template>

<style scoped>
/* Optional: Add any specific styling you need here */
</style>
