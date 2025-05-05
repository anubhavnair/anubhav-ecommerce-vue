<template>
  <div class="products border-1 border-zinc-300 rounded-2xl w-full">
    <div class="w-64 overflow-hidden  rounded-2xl">
      <img 
        :src="product.image"  
        class="rounded-lg w-full h-64 object-cover hover:scale-105 transition-transform duration-300" 
        :alt="product.title"
      />
    </div>
    <div class="px-3 py-2">
      <h1 class="font-bold text-sm">{{ product.title }}</h1>
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
      <p class="font-bold">&#8377;{{ product.price }} /-</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductComponent",
  props: {
    product: {
      type: Object,
      required: true,
      default: () => ({
        title: 'Product Title',
        image: 'https://cdn.dummyjson.com/products/images/mens-shirts/Man%20Plaid%20Shirt/thumbnail.png',
        rating: 4.5,
        price: 500
      })
    }
  }
};
</script>