<script setup>
  import Card from './Card.vue';

  defineProps({
    items: Array,
    isFavorites: Boolean
  });

  const emit = defineEmits(['addToFavorite', 'addToCart'])

</script>

<template>
  <div class="grid grid-cols-4 gap-5 " v-auto-animate>
    <Card v-for="item in items" :key="item.id"
          :id="item.id"
          :title= "item.title"
          :imgUrl="item.imageUrl"
          :price="item.price"
          :onClickAdd="isFavorites ? null : () => emit('addToCart', item)"
          :onClickFavorite="isFavorites ? null : ()=>emit('addToFavorite', item)"
          :isFavorite="item.isFavorite"
          :isAdded="item.isAdded"
    />
  </div>
</template>