<script setup lang="ts" >
import { ref } from 'vue'
      const name = ref("John Doe");
      const shoppingCart = ref([]);
      const productCount = ref(0);


  const addProduct = () => {
    productCount = 0;
  }

</script>

<template>
  <h1>Shoes {{ name }}</h1>
  <span>
    <ul>
      <li v-for="product in shoppingCart" :key="product"> {{ product }}</li>
    </ul>
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
