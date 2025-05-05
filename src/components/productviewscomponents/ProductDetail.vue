<template>
  <div v-if="loading" class="p-4 text-center">
    <i class="ri-loader-4-line animate-spin text-2xl"></i>
    Loading...
  </div>
  <div v-else-if="error" class="p-4 text-red-500 text-center">{{ error }}</div>
  <div v-else class="px-5 py-3">
    <div class="w-full rounded-2xl flex-col justify-center gap-2 md:flex md:flex-row">
      <!-- Product Images Section -->
      <div class="flex-col">
        <div class="w-full md:w-72">
          <img
            :src="currentImage"
            :alt="product.title"
            class="rounded-lg w-full h-auto object-cover"
          />
        </div>
        <div class="flex gap-5 justify-start items-center mt-5 md:w-1/2">
          <div 
            v-for="(image, index) in product.images.slice(0, 3)" 
            :key="index"
            class="w-32 cursor-pointer hover:opacity-75 transition-opacity"
            @click="currentImage = image"
          >
            <img :src="image" :alt="`${product.title} view ${index + 1}`" class="rounded-lg w-full"/>
          </div>
        </div>
      </div>

      <!-- Product Details Section -->
      <div class="mt-2">
        <div class="px-3 py-2 border-b-1 border-slate-200 pb-2">
          <h1 class="font-bold text-sm md:text-2xl">{{ product.title }}</h1>
          <p>
            <i 
              v-for="star in 5" 
              :key="star"
              :class="[
                star <= Math.floor(product.rating) ? 'ri-star-fill' : 
                star - product.rating <= 0.5 ? 'ri-star-half-line' : 'ri-star-line',
                'text-yellow-400'
              ]"
            ></i>
            <em class="p-2">{{ product.rating }}/5</em>
          </p>
          <div class="font-bold flex gap-2">
            <h3>&#8377;{{ product.price }}</h3>
            <h3 class="line-through text-slate-300">
              &#8377;{{ Math.round(product.price * (1 + product.discountPercentage/100)) }}
            </h3>
          </div>
          <p class="text-xs text-justify md:text-md">{{ product.description }}</p>
        </div>

        <!-- Color Selection -->
        <div class="inline-block">
          <section class="px-2 border-b-slate-300 border-b-1 pb-5">
            <h1 class="text-md uppercase mb-2">Select Color</h1>
            <div class="flex gap-1 justify-start text-xl">
              <label 
                v-for="color in colors" 
                :key="color.id" 
                class="cursor-pointer"
              >
                <input
                  type="radio"
                  name="color"
                  :value="color.name"
                  v-model="selectedColor"
                  class="hidden peer"
                />
                <span
                  :class="[
                    'w-8 h-8 rounded-full border-2 border-gray-300 block',
                    `bg-${color.class}`,
                    `peer-checked:ring-2 peer-checked:ring-${color.class}`
                  ]"
                ></span>
              </label>
            </div>
          </section>

          <!-- Size Selection -->
          <section class="px-2">
            <h1 class="text-md uppercase mb-2">Choose Size</h1>
            <div class="flex gap-4 justify-start">
              <button
                v-for="size in sizes"
                :key="size"
                :class="[
                  'px-4 py-2 border-2 border-gray-300 rounded-lg text-sm font-semibold cursor-pointer transition',
                  selectedSize === size ? 'bg-black text-white' : 'hover:bg-gray-200'
                ]"
                @click="selectedSize = size"
              >
                {{ size }}
              </button>
            </div>
          </section>

          <!-- Quantity Selection -->
          <section class="px-4 py-4">
            <h1 class="text-md uppercase mb-4 font-normal">Select Quantity</h1>
            <div class="flex items-center gap-4">
              <div class="flex items-center border border-gray-300 rounded-lg">
                <button
                  class="px-4 py-2 text-lg font-bold text-gray-700 hover:bg-gray-200 transition"
                  @click="decreaseQuantity"
                  :disabled="quantity <= 1"
                >
                  -
                </button>
                <input
                  type="number"
                  v-model.number="quantity"
                  min="1"
                  :max="product.stock"
                  class="w-12 text-center text-black border-none focus:outline-none"
                />
                <button
                  class="px-4 py-2 text-lg font-bold text-gray-700 hover:bg-gray-200 transition"
                  @click="increaseQuantity"
                  :disabled="quantity >= product.stock"
                >
                  +
                </button>
              </div>

              <button
                @click="addToCart"
                class="px-4 py-2 text-sm bg-black text-white rounded-lg font-semibold hover:bg-gray-800 transition"
                :disabled="!selectedSize || !selectedColor"
              >
                Add to Cart
              </button>
            </div>
          </section>
        </div>
      </div>
    </div>

    <!-- Tabs Section -->
    <section class="multiple sections">
      <div class="flex gap-5 md:gap-20 md:justify-center justify-between font-roboto text-sm p-5 font-semibold">
        <button
          :class="{ border_bottom: isActivedetail }"
          @click="handleDetail"
          class="py-2"
        >
          Product Details
        </button>
        <button 
          :class="{ border_bottom: isActiveReview }" 
          @click="handleReview"
          class="py-2"
        >
          Ratings & Reviews
        </button>
        <button 
          :class="{ border_bottom: isActiveFaq }" 
          @click="handleFaq"
          class="py-2"
        >
          FAQs
        </button>
      </div>
    </section>
    <component :is="tab" :product="product" />
  </div>
</template>

<script>
import ProductsDetailRating from "./ProductsDetailRating.vue";
import ProductReview from "./ProductReview.vue";
import ProductFaq from "./ProductFaq.vue";

export default {
  name: "ProductDetail",
  components: {
    ProductFaq,
    ProductReview,
    ProductsDetailRating,
  },
  props: {
    productId: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      product: null,
      loading: true,
      error: null,
      currentImage: '',
      quantity: 1,
      selectedColor: null,
      selectedSize: null,
      tab: "ProductReview",
      isActivedetail: false,
      isActiveReview: true,
      isActiveFaq: false,
      colors: [
        { id: 1, name: 'blue', class: 'blue-300' },
        { id: 2, name: 'red', class: 'red-300' },
        { id: 3, name: 'green', class: 'green-300' }
      ],
      sizes: ['S', 'M', 'L']
    };
  },
  async created() {
    try {
      const response = await fetch(`https://dummyjson.com/products/${this.productId}`);
      if (!response.ok) throw new Error('Product not found');
      this.product = await response.json();
      this.currentImage = this.product.images[0];
    } catch (err) {
      this.error = err.message;
    } finally {
      this.loading = false;
    }
  },
  methods: {
    increaseQuantity() {
      if (this.quantity < this.product.stock) {
        this.quantity++;
      }
    },
    decreaseQuantity() {
      if (this.quantity > 1) {
        this.quantity--;
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
    addToCart() {
      if (!this.selectedSize || !this.selectedColor) {
        alert('Please select size and color');
        return;
      }
      
      const cartItem = {
        id: this.product.id,
        title: this.product.title,
        price: this.product.price,
        quantity: this.quantity,
        size: this.selectedSize,
        color: this.selectedColor,
        image: this.currentImage
      };
      
      this.$emit('add-to-cart', cartItem);
    }
  }
};
</script>

<style scoped>
.border_bottom {
  border-bottom: 1px solid black;
}
</style>