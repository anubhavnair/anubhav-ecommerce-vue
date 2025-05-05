<template>
  <main>
  <!-- {{ $route.params.id }} -->
    <DiscountPopUp/>
    <Navbar/>
    <ProductDetail :productId="$route.params.id"/>
   <Footer/>
  </main>
</template>

<script>
import DiscountPopUp from '@/components/homeviewscomponents/DiscountPopUp.vue';
import Footer from '@/components/homeviewscomponents/Footer.vue';
import Navbar from '@/components/homeviewscomponents/Navbar.vue';
import ProductDetail from '@/components/productviewscomponents/ProductDetail.vue';

export default {
  name: "ProductDetailView",
  components:{
    Navbar,
    ProductDetail,
    Footer,
    DiscountPopUp
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