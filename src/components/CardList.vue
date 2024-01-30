<script setup>
import Card from './Card.vue'

defineProps({
  items: Array,
  isFavorites: Boolean
})

const emits = defineEmits(['addToFavorite', 'addToCart'])
</script>

<template>
  <div class="grid grid-cols-4 gap-5" v-auto-animate>
    <Card
      :key="item.key"
      v-for="item in items"
      :title="item.title"
      :image-url="item.imageUrl"
      :price="item.price"
      :is-favorite="item.isFavorite"
      :is-added="item.isAdded"
      :on-click-favorite="isFavorites ? null : () => emits('addToFavorite', item)"
      :on-click-add="isFavorites ? null : () => emits('addToCart', item)"
    />
  </div>
</template>
