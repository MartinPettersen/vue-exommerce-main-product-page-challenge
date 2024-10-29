<script lang="ts" setup>
  import { defineProps } from 'vue';
  //import type { Ref } from 'vue';

  const props = defineProps<{
    image: string;
    thumbnail: string;
    action: (image: string) => void;
    selectedImage: string;
  }>();

</script>


<template>
  <button @click="props.action(props.image)">
    <div class="rounded-lg border-2 border-[color:hsl(26,100%,55%)]">
      <img
        :class="{
          'opacity-30': props.selectedImage === props.image,
          'opacity-100': props.selectedImage !== props.image,
        }"
        class="h-16 w-auto rounded-lg"
        v-bind:src="props.thumbnail"
      />
    </div>
  </button>
</template>
