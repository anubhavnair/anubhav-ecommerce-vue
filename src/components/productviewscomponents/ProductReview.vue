<template>
  <div>
    <div class="flex justify-between p-5 gap-2">
      <h1>All Reviews (426)</h1>
      <div class="flex gap-2">
        <i class="ri-equalizer-line text-2xl"></i>
        <button class="bg-black text-white rounded-xl px-3 text-sm py-2 cursor-pointer">
          Write a Review
        </button>
      </div>
    </div>
    <div class="flex-col md:flex md:flex-row justify-center items-center">
      <CustomerReview />
      <CustomerReview />
      <CustomerReview />
    </div>
    <div class="my-2">
      <h1
        class="text-center w-fit mx-auto px-5 py-2 outline-1 rounded-xl cursor-pointer hover:bg-black hover:text-white"
      >
        Load More Reviews
      </h1>
    </div>
  </div>
</template>

<script>
import CustomerReview from "../homeviewscomponents/CustomerReview.vue";

export default {
  name: "ProductReview",
  components: {
    CustomerReview,
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

<style scoped>
/* Your styles here */
</style>
