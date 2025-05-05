<template>
  <div class="products  border-1 rounded-2xl">
    <div class="w-64 overflow-hidden bg-slate-300  rounded-2xl">
      <img 
        src="https://cdn.dummyjson.com/products/images/mens-shirts/Man%20Plaid%20Shirt/thumbnail.png"  
        class="rounded-lg w-full h-64 object-cover hover:scale-105 transition-transform duration-300" 
        alt="Product Image"
      />
    </div>
    <div class="px-3 py-2">
      <h1 class="font-bold text-sm">T-SHIRT WITH TAPE DETAILS</h1>
      <p>
        <i class="ri-star-fill text-yellow-400"></i>
        <i class="ri-star-fill text-yellow-400"></i>
        <i class="ri-star-fill text-yellow-400"></i>
        <i class="ri-star-fill text-yellow-400"></i>
        <i class="ri-star-half-line text-yellow-400"></i>
        <em class="p-2">4.5/5</em>
      </p>
      <p class="font-bold">&#8377;100 /-</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Productcomponent",
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
