<script>
export default {
    props: {
        products: {
            type: Array,
            required: true
        }
    },
    data() {
        return {
            hover: new Array(this.products.length).fill(false)
        };
    }
}
</script>

<template>
    <div>
        <div v-for="(product, i) in products" class="container_products">
            <section class="products">
                <div class="product" @mouseenter="hover[i] = true" @mouseleave="hover[i] = false">
                    <div class="img-container">
                        <img :src="(`${product.frontImage}`)" alt="">
                        <img class="display_hover" :src="(`${product.backImage}`)" alt="" v-if="hover[i]">
                    </div>

                    <span class="hearts">{{ product.hearts }}</span>

                </div>
                <div>
                    <span>{{ product.brand }}</span>
                    <h5>{{ product.name }}</h5>
                    <span class="price_now">{{ product.price }}</span>
                    <span class="discount">{{ product.discount }}</span>
                </div>
            </section>
        </div>
    </div>
</template>



<style></style>
