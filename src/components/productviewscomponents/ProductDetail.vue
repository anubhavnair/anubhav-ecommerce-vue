<template>
  <div class="px-5 py-3">
    <!-- Your template here -->
    <div
      class="w-full rounded-2xl flex-col justify-center gap-2 md:flex md:flex-row"
    >
      <div class="flex-col">
        <div class="w-full md:w-72">
          <img
            src="../../assets/productdetail_assets/image_prod_1.png"
            alt=""
          />
        </div>
        <div class="flex gap-5 justify-start items-center mt-5 md:w-1/2">
          <div class="w-32">
            <img
              src="../../assets/productdetail_assets/image_prod_2.png"
              alt=""
            />
          </div>
          <div class="w-32">
            <img
              src="../../assets/productdetail_assets/image_prod_5.png"
              alt=""
            />
          </div>
          <div class="w-32">
            <img
              src="../../assets/productdetail_assets/image_prod_6.png"
              alt=""
            />
          </div>
        </div>
      </div>

      <div class="mt-2">
        <div class="px-3 py-2 border-b-1 border-slate-200 pb-2">
          <h1 class="font-bold text-sm md:text-2xl">
            T-SHIRT WITH TAPE DETAILS
          </h1>
          <p>
            <i class="ri-star-fill text-yellow-400"></i>
            <i class="ri-star-fill text-yellow-400"></i>
            <i class="ri-star-fill text-yellow-400"></i>
            <i class="ri-star-fill text-yellow-400"></i>
            <i class="ri-star-half-line text-yellow-400"></i>
            <em class="p-2">4.5/5</em>
          </p>
          <div class="font-bold flex gap-2">
            <h3>&#8377;100 /-</h3>
            <h3 class="line-through text-slate-300">&#8377;300</h3>
          </div>
          <p class="text-xs text-justify md:text-md">
            This graphic t-shirt which is perfect for any occasion. Crafted from
            a soft and breathable fabric, it offers superior comfort and style.
          </p>
        </div>
        <div class="inline-block">
          <section class="px-2 border-b-slate-300 border-b-1 pb-5">
            <h1 class="text-md uppercase mb-2">Select Color</h1>
            <div class="flex gap-1 justify-start text-xl">
              <!-- Blue Radio Button -->
              <label class="cursor-pointer">
                <input
                  type="radio"
                  name="color"
                  id="color-blue"
                  class="hidden peer"
                />
                <span
                  class="w-8 h-8 rounded-full bg-blue-300 border-2 border-gray-300 peer-checked:border-blue-100 peer-checked:ring-2 peer-checked:ring-blue-300 block"
                ></span>
              </label>

              <!-- Red Radio Button -->
              <label class="cursor-pointer">
                <input
                  type="radio"
                  name="color"
                  id="color-red"
                  class="hidden peer"
                />
                <span
                  class="w-8 h-8 rounded-full bg-red-300 border-2 border-gray-300 peer-checked:border-red-500 peer-checked:ring-2 peer-checked:ring-red-300 block"
                ></span>
              </label>

              <!-- Green Radio Button -->
              <label class="cursor-pointer">
                <input
                  type="radio"
                  name="color"
                  id="color-green"
                  class="hidden peer"
                />
                <span
                  class="w-8 h-8 rounded-full bg-green-300 border-2 border-gray-300 peer-checked:border-green-500 peer-checked:ring-2 peer-checked:ring-green-300 block"
                ></span>
              </label>
            </div>
          </section>
          <section class="px-2">
            <h1 class="text-md uppercase mb-2">Choose Size</h1>
            <div class="flex gap-4 justify-start">
              <!-- Small Size -->
              <button
                class="px-4 py-2 border-2 border-gray-300 rounded-lg text-sm font-semibold cursor-pointer hover:bg-gray-200 focus:bg-black focus:text-white transition"
              >
                S
              </button>

              <!-- Medium Size -->
              <button
                class="px-4 py-2 border-2 border-gray-300 rounded-lg text-sm font-semibold cursor-pointer hover:bg-gray-200 focus:bg-black focus:text-white transition"
              >
                M
              </button>

              <!-- Large Size -->
              <button
                class="px-4 py-2 border-2 border-gray-300 rounded-lg text-sm font-semibold cursor-pointer hover:bg-gray-200 focus:bg-black focus:text-white transition"
              >
                L
              </button>
            </div>
          </section>
          <section class="px-4 py-4">
            <h1 class="text-md uppercase mb-4 font-normal">Select Quantity</h1>
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

              <!-- Add to Cart Button -->
              <button
                class="px-2 py-2 text-sm bg-black text-white rounded-lg font-semibold hover:bg-gray-800 transition"
              >
                Add to Cart
              </button>
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
  <section class="multiple sections">
    <div
      class="flex gap-5 md:gap-20 md:justify-center justify-between font-roboto text-sm p-5 font-semibold"
    >
      <button
        :class="{ border_bottom: isActivedetail }"
        v-on:click="handleDetail()"
        class="py-2"
        
      >
        Product Details
      </button>
      <button :class="{ border_bottom: isActiveReview }" v-on:click="handleReview()"  class="py-2">
        Ratings & Reviews
      </button>
      <button :class="{ border_bottom: isActiveFaq }" v-on:click="handleFaq()"  class="py-2 transition duration-1000">
        FAQs
      </button>
    </div>
  </section>
  <component :is="tab" />
</template>

<script>
import ProductsDetailRating from "./ProductsDetailRating.vue";
import ProductReview from "./ProductReview.vue";
import ProductFaq from "./ProductFaq.vue";

export default {
  name: "ProductDetailRating",
  components: {
    ProductFaq,
    ProductReview,
    ProductsDetailRating,
  },
  data() {
    return {
      // Your data here
      quantity: 1,
      tab: "ProductReview",
      isActivedetail: false,
      isActiveReview: true,
      isActiveFaq: false,
    };
  },
  methods: {
    // Your methods here
    increaseQuantity() {
      this.quantity += 1;
    },
    decreaseQuantity() {
      if (this.quantity > 0) {
        this.quantity -= 1;
      }
    },
    handleFaq() {
      this.isActiveReview = false;
      this.isActivedetail = false;
      this.tab = "ProductFaq";
      this.isActiveFaq = true;
    },
    handleDetail() {
      this.isActiveFaq = false;
      this.isActiveReview = false;
      this.tab = "ProductsDetailRating";
      this.isActivedetail = true;
    },
    handleReview() {
      this.isActiveFaq = false;
      this.isActivedetail = false;
      this.tab = "ProductReview";
      this.isActiveReview = true;
    },
  },
};
</script>

<style scoped>
/* Your styles here */
.border_bottom {
  border-bottom: 1px solid black;
}
</style>
