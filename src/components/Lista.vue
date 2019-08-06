<template>
    <div class="list-group">
        <ul class="list-group-item">
            <li><Item :key="obj" v-for="obj in object" :title="obj.title" :price="obj.price"
            :imgUrl="obj.thumbnail"></Item></li>
        </ul>
        
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

</style>
