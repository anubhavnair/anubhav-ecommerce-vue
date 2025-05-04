<template>
  <div class="cart-product px-5 md:flex   gap-5 border-slate-300 border-1 p-3 rounded-xl mt-2">
    <div class="w-full md:w-32">
      <img src="../../assets/productdetail_assets/image_prod_1.png" class="" alt="" />
    </div>
    <div>
      <div class="flex justify-between gap-10">
        <h1 class="font-bold text-2xl">Gradient Graphic T-shirt</h1>
        <i class="ri-delete-bin-line text-red-500 cursor-pointer text-xl "></i>
      </div>
      <div>
        <p class="text-md">Size:Large</p>
        <p class="text-sm">Color:White</p>
        <div class="flex items-center justify-between">
          <p class="font-semibold">Price: ₹500</p>
          <section class="px-4 py-4">
         
            <div class="flex items-center gap-4">
              <!-- Quantity Selector -->
              <div class="flex items-center border border-gray-300 rounded-lg">
                <button
                  class="px-4 py-2 text-lg font-bold text-gray-700 hover:bg-gray-200 transition"
                  @click="decreaseQuantity()"
                >
                  -
                </button>
                <input
                  type="number"
                  id="quantity"
                  v-model="quantity"
                  min="1"
                  class="w-12 text-center text-black border-none focus:outline-none"
                />
                <button
                  class="px-4 py-2 text-lg font-bold text-gray-700 hover:bg-gray-200 transition"
                  @click="increaseQuantity()"
                >
                  +
                </button>
              </div>

           
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CartProduct",
  data() {
    return {
      // Your data here
      quantity:1
    };
  },
  methods: {
    // Your methods here
    increaseQuantity() {
      this.quantity++;
    },
    decreaseQuantity() {
      if (this.quantity > 1) {
        this.quantity--;
      }
    }
  },
};
</script>

<style scoped>
/* Your styles here */
</style>
