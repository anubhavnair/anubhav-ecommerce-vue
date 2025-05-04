<template>
 <Navbar/>
 <CartDetail/>
 <Footer/>
</template>

<script>
import CartDetail from '@/components/cartviewcomponents/CartDetail.vue';
import Footer from '@/components/homeviewscomponents/Footer.vue';
import Navbar from '@/components/homeviewscomponents/Navbar.vue';

export default {
  name: "",
  components:{
    Navbar,
    Footer,
    CartDetail,
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
