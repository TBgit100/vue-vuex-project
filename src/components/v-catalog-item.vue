<template>
  <div class="v-catalog-item">
    <img
     class="v-catalog-item__image"
     :src="require('../assets/images/' + product_data.image)" 
     alt="picture"
     >
    <p class="v-catalog-item__name">{{ product_data.name}}</p>
    <p class="v-catalog-item__price">{{ product_data.price}}</p>
    <p class="v-catalog-item__category">{{ product_data.category}}</p>
    <p class="v-catalog-item__price">{{ product_data.about}}</p>
    <button class="v-catalog-item__add_to_cart_btn" @click="addToCart">Add to cart</button>
  </div>
</template>

<script>
export default {
    name: 'v-catalog-item',
    props: {
        product_data: {
            type: Object,
            default(){
                return {};
            }
        }
    },
    data(){
        return{}
    },
    methods:{
        addToCart(){
            this.$emit('addToCart', this.product_data)
        },
    }

}
</script>

<style>
    .v-catalog-item{
        flex-basis: 35%;
        box-shadow: 0 0 8px 0 grey;
        padding: 20px;
        margin: 20px;
    }

    .v-catalog-item__image{
        width: 160px;
        display: block;
        margin: 0 auto;
    }
</style>