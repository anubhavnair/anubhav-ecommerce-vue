<template>
  <div class="w-full p-5 border-b-1 border-b-slate-400 relative md:mt-20">
    <div
      class="md:absolute md:-top-10 md:left-100 bg-black w-full md:w-1/2 md:mx-auto min-h-[20rem] rounded-xl text-white p-5 md:flex md:justify-center md:gap-5 md:items-center md:min-h-[10vh]"
    >
      <h1
        class="text-2xl font-bold font-roboto tracking-wide leading-8 text-center md:text-4xl"
      >
        STAY UPTO DATE ABOUT OUR LATEST OFFERS
      </h1>
      <div class="mt-3 flex flex-col items-center justify-center">
        <span class="flex justify-center items-center">
          <i
            class="ri-mail-line bg-white text-black text-2xl font-light p-2 rounded-l-2xl"
          ></i>
          <input
            type="email"
            name=""
            id=""
            class="bg-white px-5 py-3 rounded-r-2xl font-light text-black"
            placeholder="example@gmail.com"
          />
        </span>
        <button class="bg-white text-black mt-5 px-22 rounded-xl py-3 mx-auto">
          Subscribe
        </button>
      </div>
    </div>
    <div
      class="md:flex justify-between items-start p-5 md:pt-30 bg-[#F2F0F1] rounded-xl"
    >
      <div class="p-2 mt-2">
        <h1 class="font-logo text-2xl md:text-4xl">SHOP.CO</h1>
        <p class="font-roboto text-xs md:text-md text-justify">
          We have clothes that suits your style and which you’re proud to wear.
          From women to men.
        </p>
        <p class="text-2xl p-2">
          <i
            class="ri-twitter-fill hover:bg-black md:text-2xl hover:text-white rounded-full"
          ></i>
          <i class="ri-instagram-fill md:text-2xl"></i>
          <i class="ri-facebook-fill md:text-2xl"></i>
          <i class="ri-github-fill md:text-2xl"></i>
        </p>
      </div>
      <div class="flex justify-between items-start p-2">
        <div>
          <h1 class="font-semibold uppercase">Company</h1>
          <span class="text-sm font-roboto flex flex-col gap-2 mt-2">
            <p>About</p>
            <p>Features</p>
            <p>Works</p>
            <p>Career</p>
          </span>
        </div>
        <div>
          <h1 class="font-semibold uppercase">Help</h1>
          <span class="text-sm font-roboto flex flex-col gap-2 mt-2">
            <p>Customer Support</p>
            <p>Delivery Details</p>
            <p>Terms & Conditions</p>
            <p>Privcy Policy</p>
          </span>
        </div>
      </div>
      <div class="flex justify-between items-center p-2">
        <div>
          <h1 class="font-semibold uppercase">FAQ</h1>
          <span class="text-sm font-roboto flex flex-col gap-2 mt-2">
            <p>Account</p>
            <p>Manage Deliveries</p>
            <p>Orders</p>
            <p>Payments</p>
          </span>
        </div>
        <div>
          <h1 class="font-semibold uppercase">Resources</h1>
          <span class="text-sm font-roboto flex flex-col gap-2 mt-2">
            <p>Free eBook</p>
            <p>Development Tutorials</p>
            <p>How to-Blog</p>
            <p>YouTUbe Playlist</p>
          </span>
        </div>
      </div>
    </div>
    <div class="w-full  px-5 py-2 flex flex-col sm:flex-row justify-between items-center">
      <p class="text-xs text-center">
        Shop.co @ 2002-2025. All Rights Reserved
      </p>
      <div class="text-2xl flex justify-center gap-5 mt-2">

        <i class="ri-visa-fill text-blue-500"></i>
        <i class="ri-mastercard-line "></i>
        <i class="ri-paypal-fill"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
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
