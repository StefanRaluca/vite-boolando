<script>
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';
import SiteFooter from './components/SiteFooter.vue';
import '@fortawesome/fontawesome-free/css/all.css';
import ProductCard from './components/ProductCard.vue';
import { state } from '../state';
import ProductModal from './components/ProductModal.vue';


export default {
  components: {
    SiteHeader,
    SiteMain,
    SiteFooter,
    ProductCard,
    ProductModal,
  },
  data() {
    return {
      productsList: state.products,
      selectedProduct: null,
      showModal: false,


    }

  },
  methods: {
    openModal(product) {
      this.selectedProduct = product;
    },
    closeModal() {
      this.selectedProduct = null;
    },
  },
}
</script>

<template>
  <SiteHeader />
  <SiteMain :products="productsList" />
  <SiteFooter />
  <!-- Show modal se e true -->
  <ProductModal v-if="selectedProduct" :product="selectedProduct" @closeModal="closeModal" />
</template>

<style lang="scss">
@import url(/src/assets/scss/main.scss);
</style>
