<script setup>

import Card from "./Card.vue";

defineProps({
  items: Array,
})

const emit = defineEmits(['addToFavorite']);

</script>

<template>
  <div class="grid grid-cols-4 gap-5" >
    <Card
        v-for="item in items"
        :key = 'item.id'
        :id="item.id"
        :image-url="item.imageUrl"
        :title="item.title"
        :price="item.price"
        :on-click-favorite="() => emit('addToFavorite', item)"
        :isFavorite ="item.isFavorite"

    />
  </div>
</template>

<style scoped>

</style>
