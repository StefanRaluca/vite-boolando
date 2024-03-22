<script>
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';
import SiteFooter from './components/SiteFooter.vue';
import '@fortawesome/fontawesome-free/css/all.css';
import ProductCard from './components/ProductCard.vue';


export default {
  components: {
    SiteHeader,
    SiteMain,
    SiteFooter,
    ProductCard,
  },
  data() {
    return {
      products: [
        {
          imgSrc: '/img/1.webp',
          discount: '-50%',
          brand: "Levi's",
          title: 'RELAXED FIT TEE UNISEX',
          priceNow: '14,99 €',
          priceBefore: '29,99 €',
          sostenibilita: 'Sostenibilità',

        },
        {
          imgSrc: '/img/2.webp',
          discount: '-30%',
          brand: 'Guess',
          title: 'ROSES TEE',
          priceNow: '20,99 €',
          priceBefore: '29,99 €',
          sostenibilita: '',



        },
        {
          imgSrc: '/img/3.webp',
          discount: '-30%',
          brand: 'Come Zucchero Filato',
          title: 'VOGLIA DI COLORI PASTELLO',
          priceNow: '12,99 €',
          priceBefore: '29,99 €',
          sostenibilita: '',


        },
        {
          imgSrc: '/img/4.webp',
          discount: '-50%',
          brand: "Levi's",
          title: 'TEE UNISEX',
          priceNow: '14,99 €',
          priceBefore: '29,99 €',
          sostenibilita: 'Sostenibilità',

        },
        {
          imgSrc: '/img/5.webp',
          discount: '',
          brand: 'Maya Deluxe',
          title: 'Stripe Bodice',
          priceNow: '99,99 €',
          priceBefore: '',
          sostenibilita: '',


        },
        {
          imgSrc: '/img/6.webp',
          discount: '',
          brand: 'Esprit',
          title: 'Maglione -Black',
          priceNow: '29,99 €',
          priceBefore: '',
          sostenibilita: 'Sostenibilità',


        }
      ],

    }

  }
}
</script>

<template>
  <SiteHeader />
  <SiteMain :products="products" />
  <SiteFooter />

</template>

<style lang="scss">
@import url(/src/assets/scss/main.scss);
</style>
