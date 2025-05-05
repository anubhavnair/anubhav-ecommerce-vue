<template>
  <DiscountPopUp/>
 <Navbar/>
 <CartDetail/>
 <Footer/>
</template>

<script>
import CartDetail from '@/components/cartviewcomponents/CartDetail.vue';
import DiscountPopUp from '@/components/homeviewscomponents/DiscountPopUp.vue';
import Footer from '@/components/homeviewscomponents/Footer.vue';
import Navbar from '@/components/homeviewscomponents/Navbar.vue';

export default {
  name: "",
  components:{
    Navbar,
    Footer,
    CartDetail,
    DiscountPopUp,
  },
  data() {
    return {
      // Your data here
    };
  },
  methods: {
    // Your methods here
  },
};
</script>

<style scoped>
/* Your styles here */
</style>
