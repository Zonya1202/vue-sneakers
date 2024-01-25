<script setup>
import Card from './Card.vue'

defineProps({
  items: Array
})

const emits = defineEmits(['addToFavorite', 'addToCart'])
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      :key="item.key"
      v-for="item in items"
      :title="item.title"
      :image-url="item.imageUrl"
      :price="item.price"
      :is-favorite="item.isFavorite"
      :is-added="item.isAdded"
      :on-click-favorite="() => emits('addToFavorite', item)"
      :on-click-add="() => emits('addToCart', item)"
    />
  </div>
</template>
