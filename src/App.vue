<script setup lang="ts">
import { ref } from 'vue'
import MainNavbar from './components/MainNavbar.vue'
import ProductShowcase from './components/ProductShowcase.vue'

const shoppingCart = ref(0)
const productCount = ref(0)
const isVisible = ref(false)

const addProduct = () => {
  shoppingCart.value = shoppingCart.value + productCount.value
  productCount.value = 0
}

const toggleCart = () => {
  console.log("isVisible.value",isVisible.value)
  isVisible.value = !isVisible.value
}
const plusOne = () => {
  productCount.value = productCount.value + 1
}
const minusOne = () =>{
  if (productCount.value > 0) {
    productCount.value = productCount.value - 1
  }
}


const deleteProduct = () => {
shoppingCart.value = 0
}

</script>
<template>
  <MainNavbar :deleteProduct="deleteProduct" :toggleCart="toggleCart" :isVisible="isVisible" :shoppingCart="shoppingCart"/>
  <ProductShowcase
    :productCount="productCount"
    :plusOne="plusOne"
    :minusOne="minusOne"
    :addProduct="addProduct"
  />
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
