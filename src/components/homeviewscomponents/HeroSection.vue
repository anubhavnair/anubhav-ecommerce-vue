<template>
  <section class="bg-[#F2F0F1] w-full py-4 px-4 sm:px-20 ">
    <div class="banner w-full flex flex-col md:flex-row items-center">
      <div class="md:pt-20 md:w-1/2">
        <h1 class="text-4xl md:text-6xl  font-hero leading-tight tracking-wider">
          FIND CLOTHES <br />THAT MATCHES <br />YOUR STYLE
        </h1>
        <p class="text-md leading-6 mt-5">
          Browse through our diverse range of meticulously crafted garments,
          designed to bring out your individuality and cater to your sense of
          style.
        </p>
        <button class="bg-black hover:bg-white hover:text-black cursor-pointer outline-1 outline-black transition duration-500 text-white px-6 py-3 rounded-full my-5 w-full md:w-1/2  ">
          Shop Now
        </button>
        <div class=" flex justify-center xl:justify-start   items-center gap-5 flex-wrap">
          <div>
            <h2 class="text-4xl text-center mb-1 font-semibold">200+</h2>
            <p class="text-center text-sm">International Brands</p>
          </div>
          <div class="border-x-2 border-slate-300 px-3">
            <h2 class="text-4xl text-center mb-1 font-semibold">2,000+</h2>
            <p class="text-center text-sm">High-Quality Products</p>
          </div>
          <div>
            <h2 class="text-4xl text-center mb-1 font-semibold">30,000+</h2>
            <p class="text-center text-sm">Happy Customers</p>
          </div>
        </div>
      </div>
      <div class=" relative bg-[url(@/assets/home_view_assets/Rectangle_3.png)] md:min-w-1/2 md:min-h-[80vh] min-w-full min-h-[80vh] bg-cover bg-center md:bg-left">
      
        <i class="ri-gemini-fill absolute left-1 top-50 text-2xl"></i>
        <i class="ri-gemini-fill text-8xl absolute right-1 top-10 md:right-20"></i>
      </div>
      
    </div>
    
  </section>
</template>

<script>
export default {
  name: "HeroSection",
};
</script>

<style scoped>
/* Scoped styles if needed */
</style>
