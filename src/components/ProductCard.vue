<script>
export default {
    props: {
        product: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            hover: false
        };
    },
    methods: {
        favoriteProduct(product) {
            product.favorite = !product.favorite;
        },
        // fa evento quando  si clicka
        showProductDetails() {
            this.$emit('showProductDetails', this.product);
        },
    }
}
</script>

<template>
    <div class="container_products">
        <section class="products">
            <div class="product" @mouseenter="hover = true" @mouseleave="hover = false">
                <div class="img-container">
                    <img :src="product.imgSrc" alt="">
                    <img class="display_hover" :src="product.imgSrc.replace('.webp', 'b.webp')" alt="" v-if="hover">
                </div>
                <!-- fa event -->
                <h5 @click="showProductDetails" :class="{ 'clickable': product.title }">{{ product.title }}</h5>
                <div v-if="product.discount" class="discount">{{ product.discount }}</div>
                <div v-if="product.sostenibilita" class="Sostenibilità">{{ product.sostenibilita }}</div>
                <div class="hearts" @click="favoriteProduct(product)">
                    <span
                        :class="{ 'fas fa-heart': product.favorite, 'far fa-heart': !product.favorite, 'red-heart': product.favorite, 'heartColor': !product.favorite }"></span>
                </div>
            </div>
            <div>
                <p>{{ product.brand }}</p>
                <!-- <h5>{{ product.title }}</h5> -->
                <span class="price_now">{{ product.priceNow }}</span>
                <span class="price_before">{{ product.priceBefore }}</span>
            </div>
        </section>
    </div>
</template>


<style>
.product h5 {
    cursor: pointer;
}
</style>
