<template>
  <div class="product">
    <strong>{{ productProp.title}} </strong>
    <p>{{ productProp.description}}</p>
    <strong>Price : {{ productProp.price }} | Adet : {{productProp.count }}</strong>
    <br><br>
    <button @click="addToCart(productProp)"> Add to Basket </button>
  </div>
</template>

<script>
export default {
    props : ["productProp"],
    methods: {
        addToCart(productProp) {
                this.$emit("addToCart",productProp)
        }
    }
}
</script>

<style>
    .product {
        border: 2px dashed #666;
        padding: 5px 10px;
        width: 300px;
        margin-right: 5px;
    }
</style>