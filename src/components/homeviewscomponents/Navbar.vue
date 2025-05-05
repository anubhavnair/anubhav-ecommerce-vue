<template>
  <nav class="flex gap-1 z-50 relative justify-between items-center bg-[#F2F0F1] w-full py-4 px-4 sm:px-20">
    <div class="flex justify-between gap-5 items-center text-normal">
      <!-- Menu Icon for Mobile -->
      <i
        class="ri-menu-line sm:hidden text-2xl font-bold text-black cursor-pointer"
        @click="toggleMenu"
      ></i>
      <RouterLink to="/">

        <h1 class="font-logo text-3xl font-normal mr-2">SHOP.CO</h1>
      </RouterLink>

      <!-- Side Menu for Mobile -->
      <div
        class="fixed inset-0 bg-black bg-opacity-50 z-50 transition-opacity duration-300 sm:hidden"
        :class="{
          'opacity-0 pointer-events-none': !isMenuOpen,
          'opacity-100': isMenuOpen,
        }"
        @click="toggleMenu"
      >
        <div
          class="fixed inset-y-0 left-0 w-64 bg-white shadow-lg transform transition-transform duration-300"
          :class="{
            '-translate-x-full': !isMenuOpen,
            'translate-x-0': isMenuOpen,
          }"
          @click.stop
        >
          <!-- Side Menu Content -->
          <div class="p-5">
            <div class="flex justify-between items-center mb-6">
              <h2 class="text-xl font-bold">Menu</h2>
              <i
                class="ri-close-line text-2xl cursor-pointer"
                @click="toggleMenu"
              ></i>
            </div>

            <!-- Mobile Menu Links -->
            <div class="flex flex-col gap-4">
              <RouterLink
                to="/"
                class="py-2 hover:bg-gray-100 rounded-lg px-3"
                @click="toggleMenu"
              >
                Home
              </RouterLink>
              <RouterLink
                to="/categories"
                class="py-2 hover:bg-gray-100 rounded-lg px-3"
                @click="toggleMenu"
              >
                Categories
              </RouterLink>
              <RouterLink
                to="/productdetail/1"
                class="py-2 hover:bg-gray-100 rounded-lg px-3"
                @click="toggleMenu"
              >
                Product Detail
              </RouterLink>
             
            </div>
          </div>
        </div>
      </div>

      <!-- Desktop Menu -->
      <div class="hidden sm:flex sm:gap-10 relative">
        <!-- Pages with Dropdown -->
        <h2 id="pages" class="relative group cursor-pointer">
          Pages <i class="ri-arrow-down-s-line"></i>
          <div
            id="pagesmenus"
            class="absolute w-70 p-5 bg-white shadow-lg rounded-lg top-5 left-0 py-3 flex-col items-center text-center hidden group-hover:flex"
          >
            <RouterLink
              to="/"
              class="hover:bg-black hover:text-white text-gray-700 py-2 px-4 rounded transition duration-300 w-full"
            >
              Home
            </RouterLink>
            <RouterLink
              to="/productdetail/1"
              class="hover:bg-black hover:text-white text-gray-700 py-2 px-4 rounded transition duration-300 w-full"
            >
              Product Detail
            </RouterLink>
            <RouterLink
              to="/categories"
              class="hover:bg-black hover:text-white text-gray-700 py-2 px-4 rounded transition duration-300 w-full"
            >
              Categories
            </RouterLink>
          </div>
        </h2>

        <!-- Other Links -->
        <!-- <h2 class="cursor-pointer hover:text-gray-600">On Sale</h2>
        <h2 class="cursor-pointer hover:text-gray-600">New Arrivals</h2>
        <h2 class="cursor-pointer hover:text-gray-600">Brands</h2> -->
      </div>

      <!-- Search Bar -->
      <div class="hidden sm:flex justify-between items-center">
        <i class="ri-search-line text-md bg-slate-200 px-4 py-2 rounded-l-2xl"></i>
        <input
          type="text"
          name="search"
          id="search"
          class="rounded-r-2xl bg-slate-200 px-30 md:px-10 py-2 w-full sm:px-5 outline-none"
          placeholder="Search For Products"
        />
      </div>
    </div>

    <!-- Cart and User Icons -->
    <div class="text-2xl flex gap-4 font-bold relative">
      <RouterLink to="/cart" class="relative">
        <i class="ri-shopping-cart-line">
          <span class="absolute -top-2 left-3 text-sm bg-black text-white rounded-full w-5 h-5 flex items-center justify-center text-xs">3</span>
        </i>
      </RouterLink>
      <i class="ri-user-line cursor-pointer hover:scale-110 transition-transform"></i>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
      document.body.style.overflow = this.isMenuOpen ? "hidden" : "";
    },
  },
  beforeDestroy() {
    document.body.style.overflow = "";
  },
};
</script>

<style scoped>
.modal-open {
  padding-right: 17px;
}
</style>