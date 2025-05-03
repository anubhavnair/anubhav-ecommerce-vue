<template>
  <main>

    <Navbar/>
    <ProductDetail/>
   <Footer/>
  </main>
</template>

<script>
import Footer from '@/components/homeviewscomponents/Footer.vue';
import Navbar from '@/components/homeviewscomponents/Navbar.vue';
import ProductDetail from '@/components/productviewscomponents/ProductDetail.vue';

export default {
  name: "ProductDetailView",
  components:{
    Navbar,
    ProductDetail,
    Footer
  },
  data() {
    return {
      // Your data here
    };
  },
  methods: {
    // Your methods here
  }
};
</script>

<style scoped>
/* Your styles here */
</style>