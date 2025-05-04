<template>
  <div class="">
    <div
      class="flex-col md:flex md:flex-row justify-center  items-start md:gap-5 gap-2 p-5 my-5 min-h-[80vh]"
    >
      <div>
        <h1 class="text-5xl uppercase font-current font-bold tracking-wide">
          Your Cart
        </h1>
        <div class="my-2">
          <CartProduct />
          <CartProduct />
          <CartProduct />
        </div>
      </div>
      <div
        class="cart-detail px-10  py-5 border border-gray-300 rounded-lg  mt-15"
      >
        <h2 class="text-xl font-bold mb-4">Order summary</h2>
        <div class="flex-col gap-3">
          <div class="flex justify-between">
            <p >SubTotal:</p>
            <p class="font-bold">₹1500/-</p>
          </div>
          <div class="flex justify-between">
            <p >Discount (20%):</p>
            <p class="font-bold">₹300/-</p>
          </div>
          <div class="flex justify-between  pb-2 border-b-black border-b-1">
            <p >Delivery Fee:</p>
            <p class="font-bold">₹50/-</p>
        
          </div>
          <div class="flex justify-between  pb-2 border-b-black border-b-1">
            <p >Total:</p>
            <p class="font-bold">₹1250/-</p>
        
          </div>
        
            <div>

                <button class=" cursor-pointer hover:bg-white hover:outline outline-1 outline-blue-300  hover:text-black bg-black text-white w-full mt-2 px-3 py-2 rounded-xl flex items-center justify-center gap-2">
                Go to Checkout
                <i class="ri-arrow-right-line"></i>
                </button>
            </div>
        
         
         
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CartProduct from "./CartProduct.vue";

export default {
  name: "CartDetail",
  components: {
    CartProduct,
  },
  data() {
    return {
      
    };
  },
 
};
</script>

<style scoped>
/* Tailwind CSS is used, so no additional styles are needed here */
</style>
