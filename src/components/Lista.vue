<template>
        <div class="list-group-item">
            <div class="list-group-item"><Item :key="obj" v-for="obj in object" :title="obj.title" :price="obj.price"
            :seller="obj.seller.id" :imgUrl="obj.thumbnail"></Item></div>
        
        <h2>
            Aqui fue
        </h2>
    </div>
</template>

<script>
import Item from './Item.vue'
export default {
    name: 'lista',
    props: ['object'],
    components: {
    Item
  },
}

</script>

<style>
    .list-group-item {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
    }
</style>
