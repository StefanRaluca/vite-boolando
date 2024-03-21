<script>
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';
import SiteFooter from './components/SiteFooter.vue';
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap';

export default {
  components: {
    SiteHeader,
    SiteMain,
    SiteFooter,
  },
  data() {
    return {

    }

  }
}
</script>

<template>
  <SiteHeader />
  <SiteMain />
  <SiteFooter />
</template>

<style></style>
