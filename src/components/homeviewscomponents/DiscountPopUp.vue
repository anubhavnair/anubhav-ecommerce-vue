<template>
  <div
    v-if="isVisible"
    class="signup-popup  duration-1000 transition-transform w-full bg-black text-white text-center flex justify-evenly p-1 items-center"
  >
    <h1
      class="md:mx-50 text-xs sm:text-sm font-abzee tracking-wide xs:text-[10px]"
    >
      Sign up and get 20% off to your first order. Sign Up Now
    </h1>
    <button 
      class="hover:cursor-pointer hover:scale-110 transition-transform" 
      @click="hidePopup"
    >
      <i class="ri-close-line text-white text-2xl xs:text-sm"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: "DiscountPopUp",
  data() {
    return {
      isVisible: true
    };
  },
  methods: {
    hidePopup() {
      this.isVisible = false;
    }
  }
};
</script>