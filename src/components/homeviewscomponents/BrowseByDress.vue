<template>
    <div class="w-full p-5 md:p-10">
      <div class="bg-[#F0F0F0] p-5 rounded-xl ">
        <h1 class="text-center text-2xl md:text-4xl font-zara font-bold uppercase mb-5">
          Browse By Dress Style
        </h1>
        <div class="flex flex-wrap justify-start gap-10">
          <!-- Casual -->
          <div class="rounded-xl relative w-full sm:w-[48%] md:w-[30%] h-[15rem] bg-[url(@/assets/home_view_assets/casual_14.png)] bg-cover bg-right-top flex items-center">
            <h1 class="absolute top-2 left-2 font-bold text-lg">Casual</h1>
          </div>
          <!-- Formal -->
          <div class=" rounded-xl relative w-full sm:w-[48%] md:w-[30%] h-[15rem] bg-[url(@/assets/home_view_assets/formal_13.png)] bg-cover bg-top-center flex items-center">
            <h1 class="absolute top-2 left-2 font-bold text-lg">Formal</h1>
          </div>
          <!-- Party -->
          <div class=" rounded-xl relative w-full sm:w-[48%] md:w-[30%] h-[15rem] bg-[url(@/assets/home_view_assets/Party_15.png)] bg-cover bg-top-right flex items-center">
            <h1 class="absolute top-2 left-2 font-bold text-lg">Party</h1>
          </div>
          <!-- Gym -->
          <div class=" rounded-xl relative w-full sm:w-[48%] md:w-[30%] h-[15rem] bg-[url(@/assets/home_view_assets/gym_16.png)] bg-cover bg-top flex items-center">
            <h1 class="absolute top-2 left-2 font-bold text-lg">Gym</h1>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "BrowseByDress",
  };
  </script>
  
  <style scoped>
  /* Add any additional custom styles here if needed */
  </style>