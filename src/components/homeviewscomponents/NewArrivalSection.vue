<template>
  <div class="mt-20">
    <h1 class="text-4xl uppercase font-logo text-center tracking-wider">
      New Arrivals
    </h1>
    <div id="newarrival" class="new-arrivals p-15 w-full flex flex-wrap justify-evenly items-center gap-2">
      <RouterLink 
        v-for="product in products" 
        :key="product.id"
        :to="`/productdetail/${product.id}`"
      >
        <ProductComponent :product="product" />
      </RouterLink>
    </div>
    
    <div class="p-5 flex justify-center mx-auto items-center w-1/2 border-b-1 border-slate-400">
      <RouterLink 
        to="/categories"
        class="text-center transition duration-500 hover:bg-black hover:text-white py-2 px-10 cursor-pointer outline-1 outline-blue-500 rounded-full"
      >
        View All
      </RouterLink>
    </div>
  </div>
</template>

<script>
import ProductComponent from "./ProductComponent.vue";

export default {
  name: "NewArrivalSection",
  components: {
    ProductComponent,
  },
  data() {
    return {
      products: []
    };
  },
  async created() {
    try {
      const response = await fetch('https://dummyjson.com/products/category/mens-shirts?limit=5');
      const data = await response.json();
      this.products = data.products.map(product => ({
        id: product.id,
        title: product.title,
        price: product.price,
        image: product.thumbnail,
        rating: product.rating
      }));
    } catch (error) {
      console.error('Error fetching products:', error);
    }
  }
};
</script>

<style scoped>
.new-arrivals {
  min-height: 400px;
}
</style>