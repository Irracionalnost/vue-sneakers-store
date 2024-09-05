<script setup>
defineProps ({
    id: Number,
    title: String,
    imageUrl: String,
    price: Number
})
const emit = defineEmits(['onCLickRemove'])
</script>


<template>
    <div class="flex items-center w-full border border-slate-100 p-4 rounded-200 gap-4">
        <img class="w-16 h-16" :src="imageUrl" :alt="title">
        <div class="flex flex-col flex-1">
            <p> {{ title }}</p>
            <div class="flex justify-between mt-2">
                <b class="flex-1"> {{ price }} руб.</b>
                <img @click="()=>emit('onCLickRemove')" class="opacity-40 hover:opacity-100 hover:cursor-pointer transition" src="/close.svg" alt="">
            </div>
        </div>
    </div>
</template>