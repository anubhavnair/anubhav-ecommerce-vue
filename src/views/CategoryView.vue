<template>
  <div >
    <Navbar />
    <div
      class="md:min-h-[90vh] md:flex md:px-20 md:py-10 mt-10 md:gap-10 w-full relative"
    >
    <div 
   
      class="md:min-w-[20%] w-full min-h-[90vh] absolute z-10 md:translate-y-0 md:relative lg:block transition-transform duration-300"
      :class="{ 'translate-y-0': isFilterVisible, '-translate-y-[150%]': !isFilterVisible }"
      ref="filter"
      
    >
        <FilterProducts :closeFilter="handleFilterSection" :isVisible="isFilterVisible" />
      </div>
      <div
        class="md:min-w-[80%] w-full overflow-hidden border-1 p-2 rounded-xl "
      >
        <div class="flex justify-between  p-3 font-current items-center">
          <h1 class="text-4xl">Casuals</h1>
          <i
            class="ri-equalizer-line text-2xl md:hidden cursor-pointer hover:scale-125 transition duration-200"
            v-on:click="handleFilterSection()"
          ></i>
        </div>
        <div
          class="rounded-xl flex flex-wrap h-fit gap-2 justify-center "
        >
          <ProductComponent />
          <ProductComponent />
          <ProductComponent />
          <ProductComponent />
          <ProductComponent />
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import FilterProducts from "@/components/categoryviewcomponents/FilterProducts.vue";
import Footer from "@/components/homeviewscomponents/Footer.vue";
import Navbar from "@/components/homeviewscomponents/Navbar.vue";
import ProductComponent from "@/components/homeviewscomponents/ProductComponent.vue";

export default {
  name: "",
  components: {
    Navbar,
    Footer,
    FilterProducts,
    ProductComponent,
  },
  data() {
    return {
      // Your data here
      isFilterVisible: false
    };
  },
  methods: {
    // Your methods here
    handleFilterSection(){

        return this.isFilterVisible = !this.isFilterVisible;
    }
  },
};
</script>

<style scoped>
/* Your styles here */
</style>
