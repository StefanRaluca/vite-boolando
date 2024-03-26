<script>
import ProductCard from './ProductCard.vue';
import axios from 'axios';
/* import { state } from '../../state' */
import ProductModal from './ProductModal.vue';

export default {
    components: {
        ProductCard,
        ProductModal,
    },
    data() {
        return {
            productList: [],
            selectedProduct: null,
        };
    },
    methods: {
        favoriteProduct(product) {
            product.favorite = !product.favorite;
        },
        recoverProducts() {
            axios.get('http://localhost:3000/productsList')
                .then(response => {
                    // console.log('start again');
                    this.productList = response.data;
                    console.log(response.data);
                })
                .catch(error => {
                    console.error('Error recovering products:', error);
                });
        },
        openModal(product) {
            console.log("open", product);
            this.selectedProduct = product;
        },
        // Metodo per chiudere la modale
        closeModal() {
            this.selectedProduct = null;
        },
    },
    mounted() {
        this.recoverProducts();
    }
};
</script>

<template>
    <div class="container_main">

        <ProductCard v-for="product in productList" :product="product" @showProductDetails="openModal" />

        <!-- Mostra la modale solo se selectedProduct è definito -->
        <ProductModal v-if="selectedProduct" :product="selectedProduct" @closeModal="closeModal" />
    </div>
</template>


<style lang="scss">
@import url(./mainStyle.scss);
</style>
