<script lang="ts" setup>
import productOne from '@/assets/image-product-1.jpg'
import productTwo from '@/assets/image-product-2.jpg'
import productThree from '@/assets/image-product-3.jpg'
import productFour from '@/assets/image-product-4.jpg'
import productOneThumbnail from '@/assets/image-product-1-thumbnail.jpg'
import productTwoThumbnail from '@/assets/image-product-2-thumbnail.jpg'
import productThreeThumbnail from '@/assets/image-product-3-thumbnail.jpg'
import productFourThumbnail from '@/assets/image-product-4-thumbnail.jpg'
import LightBox from './LightBox.vue'
import previousIcon from '@/assets/icon-previous.svg'
import nextIcon from '@/assets/icon-next.svg'

import { ref, onMounted, onUnmounted } from 'vue'
import ImageButton from './ImageButton.vue'

const selectedImage = ref(productOne)
const lightBoxVisible = ref(false)

// eslint-disable-next-line @typescript-eslint/no-explicit-any
const swapImage = (image: any) => {
  selectedImage.value = image
}

const toggleLightBox = () => {
  lightBoxVisible.value = !lightBoxVisible.value
}

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

const imageList = ref([productOne, productTwo, productThree, productFour])
const index = ref(0)

const plusOne = () => {
  if (index.value < 3) {
    index.value = index.value + 1
  } else {
    index.value = 0
  }
  swapImage(imageList.value[index.value])
}
const minusOne = () => {
  if (index.value > 0) {
    index.value = index.value - 1
  } else {
    index.value = 3
  }
  swapImage(imageList.value[index.value])
}

</script>

<template>
  <div class="flex flex-col items-center justify-center">
    <div class="flex items-center justify-center" @click="() => toggleLightBox()">
      <img class="w-full md:w-[70%] h-auto md:rounded-lg" v-bind:src="selectedImage" />
      <div v-if="isMobile" class="w-[87%] z-10 absolute flex justify-between" @click.stop>
          <div class="bg-white rounded-full px-4 py-3 hover:cursor-pointer">
            <img
              class="w-4 h-auto rounded-lg hover:text-orange-400"
              v-bind:src="previousIcon"
              @click="() => minusOne()"
            />
          </div>
          <div class="bg-white rounded-full px-4 py-3 hover:cursor-pointer">
            <img
              class="w-4 h-auto rounded-lg hover:text-orange-400"
              v-bind:src="nextIcon"
              @click="() => plusOne()"
            />
          </div>
        </div>
    </div>
    <div v-if="!isMobile" class="flex w-[70%] justify-between pt-4">

      <ImageButton :action="swapImage" :image="productOne" :thumbnail="productOneThumbnail" :selectedImage="selectedImage"/>

      <ImageButton :action="swapImage" :image="productTwo" :thumbnail="productTwoThumbnail" :selectedImage="selectedImage"/>

      <ImageButton :action="swapImage" :image="productThree" :thumbnail="productThreeThumbnail" :selectedImage="selectedImage"/>

      <ImageButton :action="swapImage" :image="productFour" :thumbnail="productFourThumbnail" :selectedImage="selectedImage"/>

    </div>
  </div>
  <LightBox :swapImage="swapImage" :selectedImage="selectedImage" :isVisible="lightBoxVisible" :toggleLightBox="toggleLightBox"/>
</template>
