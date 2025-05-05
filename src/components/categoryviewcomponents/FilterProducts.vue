<template>
  <div class="border-1 border-slate-400 rounded-xl min-h-full bg-white">
    <!-- Header -->
    <div class="flex justify-between p-5 border-b border-slate-300">
      <h1 class="font-bold">Filters</h1>
      <i
        class="ri-equalizer-line cursor-pointer xs:hidden md:block hover:scale-125 transition duration-200"
      ></i>
      <i class="ri-close-line md:hidden" v-on:click="closeFilter"></i>
    </div>

    <!-- Categories -->
    <section class="p-5 flex-col gap-3 font-light border-b border-slate-300">
      <h2 class="font-bold mb-3">Categories</h2>
      <div class="flex flex-col gap-2">
        <div
          v-for="category in categories"
          :key="category.name"
          class="flex justify-between items-center cursor-pointer hover:bg-gray-50 p-2 rounded"
          @click="toggleCategory(category.name)"
        >
          <span class="text-sm">{{ category.name }}</span>
          <i
            class="ri-arrow-right-s-line transition-transform duration-200"
            :class="{ 'rotate-90': selectedCategories.includes(category.name) }"
          ></i>
        </div>
      </div>
    </section>

    <!-- Price Range -->
    <section class="p-5 border-b border-slate-300">
      <div>
        <h2 class="font-bold mb-3">Price Range</h2>
        <div
          class="flex justify-center gap-5 items-center lg:flex-col xl:flex-row"
        >
          <input
            type="range"
            name="price"
            id="price"
            min="0"
            max="100000"
            step="1000"
            ref="filter_price"
            @input="handlePriceChange"
            class="w-full"
          />
          <p>₹{{ selectedPrice }}</p>
        </div>
      </div>
    </section>

    <!-- Size Filter -->
    <section class="p-5 border-b border-slate-300">
      <h2 class="font-bold mb-3">Size</h2>
      <div class="flex flex-wrap gap-2">
        <button
          v-for="size in sizes"
          :key="size"
          @click="toggleSize(size)"
          :class="[
            'px-4 py-2 border rounded-lg text-sm',
            selectedSizes.includes(size)
              ? 'bg-black text-white'
              : 'hover:bg-gray-100',
          ]"
        >
          {{ size }}
        </button>
      </div>
    </section>

    <!-- Color Filter -->
    <section class="p-5 border-b border-slate-300">
      <h2 class="font-bold mb-3">Color</h2>
      <div class="flex flex-wrap gap-3">
        <div
          v-for="color in colors"
          :key="color.name"
          @click="toggleColor(color.name)"
          :class="[
            'w-8 h-8 rounded-full cursor-pointer border-2',
            selectedColors.includes(color.name) ? 'ring-2 ring-black' : '',
          ]"
          :style="{ backgroundColor: color.hex }"
        ></div>
      </div>
    </section>

    <!-- Brand Filter -->
    <section class="p-5 border-b border-slate-300">
      <h2 class="font-bold mb-3">Brands</h2>
      <div class="flex flex-col gap-2">
        <label
          v-for="brand in brands"
          :key="brand"
          class="flex items-center gap-2 text-sm cursor-pointer hover:bg-gray-50 p-1 rounded"
        >
          <input
            type="checkbox"
            :value="brand"
            v-model="selectedBrands"
            class="accent-black"
          />
          {{ brand }}
        </label>
      </div>
    </section>

    <!-- Clear Filters -->
    <section class="p-5">
      <button
        @click="clearFilters"
        class="w-full py-2 bg-black text-white rounded-lg hover:bg-gray-800 transition"
      >
        Clear All Filters
      </button>
      <button
        @click="applyFilters"
        class="w-full py-2 bg-black text-white rounded-lg hover:bg-gray-800 transition mt-2"
      >
        Apply
      </button>
    </section>
  </div>
</template>

<script>
export default {
  name: "FilterProducts",
props:{

  closeFilter:Function,
  isVisible:Boolean
},
  data() {
    return {
      
      selectedPrice: 0,
      sizes: ["XS", "S", "M", "L", "XL", "XXL"],
      selectedSizes: [],
      colors: [
        { name: "White", hex: "#FFFFFF" },
        { name: "Black", hex: "#000000" },
        { name: "Red", hex: "#FF0000" },
        { name: "Blue", hex: "#0000FF" },
        { name: "Green", hex: "#00FF00" },
      ],
      selectedColors: [],
      brands: ["Nike", "Adidas", "Puma", "Reebok", "Under Armour"],
      selectedBrands: [],
      categories: [
        { name: "T-Shirts", count: 120 },
        { name: "Shorts", count: 89 },
        { name: "Shirts", count: 204 },
        { name: "Hoodies", count: 165 },
        { name: "Jeans", count: 150 },
      ],
      selectedCategories: [],
    };
  },
  methods: {
    handlePriceChange() {
      this.selectedPrice = this.$refs.filter_price.value;
    },
    toggleSize(size) {
      const index = this.selectedSizes.indexOf(size);
      if (index === -1) {
        this.selectedSizes.push(size);
      } else {
        this.selectedSizes.splice(index, 1);
      }
    },
    toggleColor(color) {
      const index = this.selectedColors.indexOf(color);
      if (index === -1) {
        this.selectedColors.push(color);
      } else {
        this.selectedColors.splice(index, 1);
      }
    },
    clearFilters() {
      this.selectedPrice = 0;
      this.selectedSizes = [];
      this.selectedColors = [];
      this.selectedBrands = [];
      if (this.$refs.filter_price) {
        this.$refs.filter_price.value = 0;
      }
    },
    applyFilters() {
      const filters = {
        price: this.selectedPrice,
        sizes: this.selectedSizes,
        colors: this.selectedColors,
        brands: this.selectedBrands,
      };
      alert(filters);
    },
    toggleCategory(category) {
      const index = this.selectedCategories.indexOf(category);
      if (index === -1) {
        this.selectedCategories.push(category);
      } else {
        this.selectedCategories.splice(index, 1);
      }
    },
  },
};
</script>

<style scoped>
input[type="range"] {
  accent-color: black;
}
</style>
