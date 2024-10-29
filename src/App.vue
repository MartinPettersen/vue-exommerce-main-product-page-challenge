<script setup lang="ts" >
import { ref } from 'vue'
      const name = ref("Cool shoes");
      const shoppingCart = ref<string[]>([]);
      const productCount = ref(1);


  const addProduct = () => {
    if (productCount.value !== 0 ){
      console.log(shoppingCart.value.length)
      //productCount.value = 0;
      shoppingCart.value.push("shoe")
    }
  }

  const deleteProduct = (index: number) => {
    shoppingCart.value.splice(index, 1)
  }

</script>

<template>
  <h1 class="text-2xl">Shoes {{ name }}</h1>
  <span>
    <ul>
      <li v-for="(product, index) in shoppingCart" :key="product">
        <span>
          {{ product }}  {{  index }}
        </span>
        <button @click="deleteProduct(index)">Remove</button>

      </li>
    </ul>
    <button @click="addProduct">Add to Cart</button>
  </span>
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
