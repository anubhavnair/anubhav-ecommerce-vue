<template>
  <div class="max-w-full pb-5">
    <!-- Header -->
    <div class="w-full flex justify-between px-10 py-5">
      <h1 class="text-xl  uppercase font-zara font-semibold">Our Happy Customers</h1>
      <p class="text-2xl">
        <i class="ri-arrow-left-s-fill"></i>
        <i class="ri-arrow-right-s-fill"></i>
      </p>
    </div>

    <!-- Reviews Section -->
    <div class="overflow-x-auto px-10  hide-scrollbar">
      <div class="flex gap-5">
        <CustomerReview />
        <CustomerReview />
        <CustomerReview />
        <CustomerReview />
        <CustomerReview />
        <CustomerReview />
      </div>
    </div>
  </div>
</template>

<script>
import CustomerReview from "./CustomerReview.vue";

export default {
  name: "OurHappyCustomer",
  components: {
    CustomerReview,
  },
};
</script>

<style scoped>
.hide-scrollbar {
  overflow-x: scroll;
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE 10+ */
}

.hide-scrollbar::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera */
}
</style>
