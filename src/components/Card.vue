<script setup>
const props = defineProps({
  id:Number,
  title: String,
  imgUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function,
})

</script>

<template>
    <div class="relative bg-white border border-slate-100 rounded-3xl p-8 cursor-pointer transition hover:-translate-y-2 hower:shadow-xl">
        <img v-if="onClickFavorite" @click="onClickFavorite" :src="isFavorite ? '/like-2.svg' : '/like-1.svg'" alt="Like 1" class="absolute top-8 left-8">
        <img :src="imgUrl" alt="Sneaker">
        <p class="mt-2">{{ title }}</p>

        <div class="flex justify-between mt-5">
          <div class="flex flex-col">
            <span class="text-slate-400">Цена:</span>
            <b>{{ price }} руб.</b>
          </div>
          <img v-if="onClickAdd" @click="onClickAdd" :src="isAdded ? 'checked.svg' : '/plus.svg'" alt="plus">
        </div>
      </div>
</template>