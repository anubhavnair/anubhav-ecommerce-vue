<template>
  <main>
    <DiscountPopUp />
    <Navbar />
    <HeroSection />
    <Brands />
    <NewArrivalSection />
    <TopSelling/>
    <BrowseByDress />
    <OurHappyCustomer />
    <Footer />
  </main>
</template>

<script>
import Brands from "./Brands.vue";
import BrowseByDress from "./BrowseByDress.vue";
import DiscountPopUp from "./DiscountPopUp.vue";
import Footer from "./Footer.vue";
import HeroSection from "./HeroSection.vue";

import Navbar from "./Navbar.vue";
import NewArrivalSection from "./NewArrivalSection.vue";
import OurHappyCustomer from "./OurHappyCustomer.vue";
import TopSelling from "./TopSelling.vue";

export default {
  name: "HomeHeader",
  components: {
    Navbar,
    HeroSection,
    DiscountPopUp,
    Brands,
    NewArrivalSection,
    TopSelling,
    BrowseByDress,
    OurHappyCustomer,
    Footer,
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

<style scoped></style>
