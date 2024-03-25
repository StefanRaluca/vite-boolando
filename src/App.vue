<script>
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';
import SiteFooter from './components/SiteFooter.vue';
import '@fortawesome/fontawesome-free/css/all.css';
import ProductCard from './components/ProductCard.vue';
import { state } from '../state';


export default {
  components: {
    SiteHeader,
    SiteMain,
    SiteFooter,
    ProductCard,

  },
  data() {
    return {
      productsList: state.products


    }

  }
}
</script>

<template>
  <SiteHeader />
  <SiteMain :products="productsList" />
  <SiteFooter />

</template>

<style lang="scss">
@import url(/src/assets/scss/main.scss);
</style>
