<script>
import ProductCard from './ProductCard.vue';

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

            /*  hover: new Array(6).fill(false) */
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

        <div class="container_main">

            <ProductCard v-for="product in productList" :product="product" />
        </div>
    </div>
</template>


<style lang="scss">
@import url(./mainStyle.scss);
</style>
