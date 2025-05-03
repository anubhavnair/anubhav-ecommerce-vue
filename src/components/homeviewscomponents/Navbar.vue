<template>
  <nav
    class="flex gap-1 justify-between items-center bg-[#F2F0F1] w-full py-4 px-4 sm:px-20"
  >
    <div class="flex justify-between gap-5 items-center text-normal">
      <i class="ri-menu-line sm:hidden text-2xl font-bold text-black"></i>
      <h1 class="font-logo text-3xl font-normal mr-2">SHOP.CO</h1>

      <div class="hidden sm:flex sm:gap-10 relative">
        <!-- Pages with Dropdown -->
        <h2 id="pages" class="relative group cursor-pointer">
          Pages <i class="ri-arrow-down-s-line"></i>
          <div
            id="pagesmenus"
            class="absolute w-70 p-5   bg-white shadow-lg rounded-lg top-5 left-0 py-3  flex-col  items-center text-center hidden group-hover:flex"
          >
            <RouterLink
              to="/"
              class="hover:bg-black hover:text-white text-gray-700 py-2 px-4 rounded transition duration-300"
            >
              Home
            </RouterLink>
            <RouterLink
              to="/productdetail/1"
              class="hover:bg-black hover:text-white text-gray-700 py-2 px-4 rounded transition duration-300"
            >
              Product Detail
            </RouterLink>
            <RouterLink
              to="/productdetail/1"
              class="hover:bg-black hover:text-white text-gray-700 py-2 px-4 rounded transition duration-300"
            >
              Product Detail
            </RouterLink>
          </div>
        </h2>

        <!-- Other Links -->
        <h2>On Sale</h2>
        <h2>New Arrivals</h2>
        <h2>Brands</h2>
      </div>

      <div class="hidden sm:flex justify-between items-center">
        <i
          class="ri-search-line text-md bg-slate-200 px-4 py-2 rounded-l-2xl"
        ></i>
        <input
          type="text"
          name="search"
          id="search"
          class="rounded-r-2xl bg-slate-200 px-30 md:px-10 py-2 w-full sm:px-5"
          placeholder="Search For Products"
        />
      </div>
    </div>

    <div class="text-2xl flex gap-4 font-bold">
      <i class="ri-shopping-cart-line"></i>
      <i class="ri-user-line"></i>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",

  data() {
    return {
      menu: false,
    };
  },
  handlemenu() {
    this.menu = !this.menu;
  },
};
</script>

<style scoped>
/* Scoped styles if needed */
#pages:hover #pagesmenus {
  display: block;
}
</style>
