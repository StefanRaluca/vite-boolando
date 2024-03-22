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
