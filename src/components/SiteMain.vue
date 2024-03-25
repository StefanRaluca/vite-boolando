<script>
import ProductCard from './ProductCard.vue';
import axios from 'axios';
/* import { state } from '../../state' */

export default {
    components: {
        ProductCard
    },
    props: {
        products: {
            type: Array,
            required: true
        }
    },
    data() {
        return {
            productList: [],
            /*    state, */


        };
    },
    methods: {
        favoriteProduct(product) {
            product.favorite = !product.favorite;
        },
        recoverProducts() {
            axios.get('http://localhost:3000/productsList')
                .then(response => {
                    this.productList = response.data;
                    console.log(response.data);
                })
                .catch(error => {
                    console.error('Error recovering products:', error);
                });
        }
    },
    mounted() {
        this.recoverProducts();
    }
};
</script>

<template>
    <div>

        <div class="container_main">

            <ProductCard v-for="product in productList" :product="product" />
        </div>
    </div>
</template>


<style lang="scss">
@import url(./mainStyle.scss);
</style>
