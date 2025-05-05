<template>
  <div>
    <DiscountPopUp />
    <Navbar />

    <div
      class="md:min-h-[90vh] md:flex md:px-20 md:py-10 mt-10 md:gap-10 w-full relative"
    >
      <div
        class="md:min-w-[20%] w-full min-h-[90vh] absolute z-10 md:translate-y-0 md:relative lg:block transition-transform duration-300"
        :class="{
          'translate-y-0': isFilterVisible,
          '-translate-y-[150%]': !isFilterVisible,
        }"
        ref="filter"
      >
        <FilterProducts
          :closeFilter="handleFilterSection"
          :isVisible="isFilterVisible"
        />
      </div>

      <div
        class="md:min-w-[80%] w-full overflow-hidden border-1 border-zinc-300 p-2 rounded-xl"
      >
        <div class="flex justify-between p-3 font-current items-center">
          <h1 class="text-4xl">All Products</h1>
        
          <i
            class="ri-equalizer-line text-2xl md:hidden cursor-pointer hover:scale-125 transition duration-200"
            @click="handleFilterSection"
          ></i>
        </div>

        <!-- Loading State -->
        <div v-if="loading" class="text-center py-10">
          <i class="ri-loader-4-line animate-spin text-3xl"></i>
          <p>Loading products...</p>
        </div>

        <!-- Error State -->
        <div v-else-if="error" class="text-center py-10 text-red-500">
          {{ error }}
        </div>

        <!-- Products Grid -->
        <div
          v-else
          class="rounded-xl flex flex-wrap h-fit gap-2 xs:justify-center md:justify-start"
        >
          <RouterLink
            v-for="product in allProducts"
            :key="product.id"
            :to="`/productdetail/${product.id}`"
          >
            <ProductComponent
              :product="{
                title: product.title,
                image: product.thumbnail,
                rating: product.rating,
                price: product.price,
              }"
            />
          </RouterLink>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import FilterProducts from "@/components/categoryviewcomponents/FilterProducts.vue";
import DiscountPopUp from "@/components/homeviewscomponents/DiscountPopUp.vue";
import Footer from "@/components/homeviewscomponents/Footer.vue";
import Navbar from "@/components/homeviewscomponents/Navbar.vue";
import ProductComponent from "@/components/homeviewscomponents/ProductComponent.vue";

export default {
  name: "CategoryView",
  components: {
    Navbar,
    Footer,
    FilterProducts,
    ProductComponent,
    DiscountPopUp,
  },
  data() {
    return {
      isFilterVisible: false,
      allProducts: [],
      allcategories: [],
      loading: true,
      error: null,
    };
  },
  async created() {
    try {
      const response = await fetch("https://dummyjson.com/products?limit=10");
      const catRes = await fetch(
        "https://dummyjson.com/products/category-list"
      );
      if (!response.ok) {
        throw new Error("Failed to fetch products");
      }
      const data = await response.json();
      const catData = await catRes.json();
      this.allcategories = catData;
      this.allProducts = data.products;
    } catch (err) {
      this.error = err.message;
      console.error("Error fetching products:", err);
    } finally {
      this.loading = false;
    }
  },
  methods: {
    handleFilterSection() {
      this.isFilterVisible = !this.isFilterVisible;
    },
  },
};
</script>

<style scoped>
/* Add any custom styles here */
</style>
