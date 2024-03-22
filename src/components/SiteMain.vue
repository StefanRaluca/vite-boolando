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
            productList: [
                {
                    imgSrc: '/img/1.webp',
                    discount: '-50%',
                    brand: "Levi's",
                    title: 'RELAXED FIT TEE UNISEX',
                    priceNow: '14,99 €',
                    priceBefore: '29,99 €',
                    sostenibilita: 'Sostenibilità',
                    hearts: '❤️'
                },
                {
                    imgSrc: '/img/2.webp',
                    discount: '-30%',
                    brand: 'Guess',
                    title: 'ROSES TEE',
                    priceNow: '20,99 €',
                    priceBefore: '29,99 €',
                    sostenibilita: '',
                    hearts: '❤️'
                },
                {
                    imgSrc: '/img/3.webp',
                    discount: '-30%',
                    brand: 'Come Zucchero Filato',
                    title: 'VOGLIA DI COLORI PASTELLO',
                    priceNow: '12,99 €',
                    priceBefore: '29,99 €',
                    sostenibilita: '',
                    hearts: '❤️'
                },
                {
                    imgSrc: '/img/4.webp',
                    discount: '-50%',
                    brand: "Levi's",
                    title: 'TEE UNISEX',
                    priceNow: '14,99 €',
                    priceBefore: '29,99 €',
                    sostenibilita: 'Sostenibilità',
                    hearts: '❤️'
                },
                {
                    imgSrc: '/img/5.webp',
                    discount: '',
                    brand: 'Maya Deluxe',
                    title: 'Stripe Bodice',
                    priceNow: '99,99 €',
                    priceBefore: '',
                    sostenibilita: '',
                    hearts: '❤️'
                },
                {
                    imgSrc: '/img/6.webp',
                    discount: '',
                    brand: 'Esprit',
                    title: 'Maglione -Black',
                    priceNow: '29,99 €',
                    priceBefore: '',
                    sostenibilita: 'Sostenibilità',
                    hearts: '❤️'
                }
            ],

            hover: new Array(6).fill(false)
        };
    },
    methods: {
        favoriteProduct(product) {
            product.favorite = !product.favorite;
        },
    }
}
</script>

<template>
    <div>
        <!-- Prima sezione di main  -->
        <div class="container_main">
            <div v-for="(product, i) in productList.slice(0, 3)" class="container_products">
                <section class="products">
                    <div class="product" @mouseenter="hover[i] = true" @mouseleave="hover[i] = false">
                        <div class="image-container">
                            <img :src="product.imgSrc" alt="">
                            <img class="display_hover" :src="product.imgSrc.replace('.webp', 'b.webp')" alt=""
                                v-if="hover[i]">
                        </div>
                        <div v-if="product.discount" class="discount">{{ product.discount }}</div>
                        <div v-if="product.sostenibilita" class="Sostenibilità">{{ product.sostenibilita }}</div>
                        <div class="hearts" @click="favoriteProduct(product)">
                            <span
                                :class="{ 'fas fa-heart': product.favorite, 'far fa-heart': !product.favorite, 'red-heart': product.favorite, 'heartColor': !product.favorite }"></span>
                        </div>
                    </div>
                    <div>
                        <span>{{ product.brand }}</span>
                        <h5>{{ product.title }}</h5>
                        <span class="price_now">{{ product.priceNow }}</span>
                        <span class="price_before">{{ product.priceBefore }}</span>
                    </div>
                </section>
            </div>
        </div>

        <!-- Seconda sezione di main  -->
        <div class="container_main">
            <div v-for="(product, i) in products.slice(3)" class="container_products">
                <section class="products">
                    <div class="product" @mouseenter="hover[i + 3] = true" @mouseleave="hover[i + 3] = false">
                        <div class="image-container">
                            <img :src="product.imgSrc" alt="">
                            <img class="display_hover" :src="product.imgSrc.replace('.webp', 'b.webp')" alt=""
                                v-if="hover[i + 3]">
                        </div>
                        <div v-if="product.discount" class="discount">{{ product.discount }}</div>
                        <div v-if="product.sostenibilita" class="Sostenibilità">{{ product.sostenibilita }}</div>
                        <div class="hearts" @click="favoriteProduct(product)">
                            <span
                                :class="{ 'fas fa-heart': product.favorite, 'far fa-heart': !product.favorite, 'red-heart': product.favorite, 'heartColor': !product.favorite }"></span>
                        </div>

                    </div>
                    <div>
                        <span>{{ product.brand }}</span>
                        <h5>{{ product.title }}</h5>
                        <span class="price_now">{{ product.priceNow }}</span>
                        <span class="price_before">{{ product.priceBefore }}</span>
                    </div>
                </section>
            </div>
        </div>
    </div>

</template>



<style lang="scss">
@import url(./mainStyle.scss);
</style>
