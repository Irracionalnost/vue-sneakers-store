<script setup>
import { ref, onMounted} from 'vue'
import axios from 'axios';
import CardList from '@/components/CardList.vue';
const favorites = ref([])

onMounted( async () => {
    try {
        const {data} = await axios.get('https://9e87f3738f6d8a9a.mokky.dev/favorites?_relations=items');
        favorites.value = data.map( (obj) => obj.item);
    }
    catch(err){
        
    }
})
</script>


<template>
    <div>
        <h2 class="text-3xl font-bold mb-8"> Мои закладки</h2>
        <CardList :items="favorites" :is-favorites="true"/>
    </div>
</template>