<template>
    <div class="card centralizar" style="width: 18rem;">
        <img class="card-img-top" :src="imgUrl" alt="Card image cap">
        <div class="card-body">
            <h1 class="card-title">{{title}}</h1>
            <p class="card-text">El precio es: ${{price}}</p>
            <p class="card-text">El vendedor es: {{seller}}</p>
        </div>
    </div>
</template>
<script>
export default {
  name: "Item",
  props: {
    title: String,
    price: Number,
    seller: String,
    imgUrl: String
  }
};
</script>

<style>
    .centralizar{
        display: block;
    margin-left: auto;
    margin-right: auto
    }
</style>