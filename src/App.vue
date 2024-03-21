<script>
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';
import SiteFooter from './components/SiteFooter.vue';
import '@fortawesome/fontawesome-free/css/all.css';


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

<style lang="scss">
@import url(./assets/main.scss);
</style>
