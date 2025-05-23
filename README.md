# Ecommerce-Frontend-vue-Anubhav

## Quick Links
- 🚀 [Live Demo](https://anubhav-ecommerce-vue.onrender.com)

## Overview

## main pages are :
1. Home View
2. Product Detail View
3. Shopping Cart View
4. Categories & Filter View

## Page Documentation

### 1. Home View (`/src/views/HomeView.vue`)

- **Key Features**:
  - Hero section with promotional content
  - New arrivals and top selling products
  - Browse by dress categories
  - Customer reviews section
- **Components**: 11 modular components
- **Screenshots**: 4 views showing responsive layouts

### 2. Product Detail View (`/src/views/ProductDetailView.vue`)

- **Key Features**:
  - Product image gallery
  - Size and color selection
  - Reviews and ratings
  - FAQ section
- **Components**: 5 specialized components
- **Screenshots**: 4 views of product details

### 3. Shopping Cart View (`/src/views/CartView.vue`)

- **Key Features**:
  - Cart items management
  - Order summary
  - Quantity adjustments
  - Checkout process
- **Components**: 3 cart-related components
- **Screenshots**: 2 views of cart interface

### 4. Categories View (`/src/views/CategoryView.vue`)

- **Key Features**:
  - Product filtering system
  - Responsive product grid
  - Mobile-friendly filter panel
  - Sort and filter options
- **Components**:
  - CategoryView
  - FilterProducts
  - ProductComponent
- **Screenshots**: 2 views showing filter functionality

## Tech Stack

- Vue.js 3
- Tailwind CSS
- Remix Icons
- Vue Router

## File Structure

```
src/
├── components/
│   ├── homeviewscomponents/
│   ├── productviewscomponents/
│   ├── cartviewcomponents/
│   └── categoryviewcomponents/
├── views/
│   ├── HomeView.vue
│   ├── ProductDetailView.vue
│   ├── CartView.vue
│   └── CategoryView.vue
└── assets/
    ├── home_view_assets/
    ├── productdetail_assets/
    ├── cartassets/
    └── categoriesassets/
```

## Getting Started

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build
```
---

# Detailed Doc



## HomeViews Components Documentation

The `homeviewscomponents` folder contains all the key components used to build the homepage of the Ecommerce Vue application. Below is a detailed explanation of each component and its purpose.

---

![Ecommerce Homepage](./src/assets/home_view_assets/Screenshot%202025-05-03%20075825.png)
![Ecommerce Homepage](./src/assets/home_view_assets/Screenshot%202025-05-03%20080031.png)
![Ecommerce Homepage](./src/assets/home_view_assets/Screenshot%202025-05-03%20080124.png)
![Ecommerce Homepage](./src/assets/home_view_assets/Screenshot%202025-05-03%20080144.png)

### 1. **HomeHeader.vue**

- **Description**: Acts as the main container for all homepage sections. It imports and organizes all the components used in the homepage.
- **Key Components Used**:
  - `DiscountPopUp`
  - `Navbar`
  - `HeroSection`
  - `Brands`
  - `NewArrivalSection`
  - `TopSelling`
  - `BrowseByDress`
  - `OurHappyCustomer`
  - `Footer`

---

### 2. **DiscountPopUp.vue**

- **Description**: Displays a promotional banner at the top of the page encouraging users to sign up for discounts.
- **Key Features**:
  - Responsive design with text and a close button.
  - Uses `remixicon` for the close icon.

---

### 3. **Navbar.vue**

- **Description**: The navigation bar for the homepage.
- **Key Features**:
  - Contains links for "Shop," "On Sale," "New Arrivals," and "Brands."
  - Includes a search bar and icons for the shopping cart and user profile.
  - Fully responsive for mobile and desktop views.

---

### 4. **HeroSection.vue**

- **Description**: The hero section of the homepage, showcasing the main tagline and promotional content.
- **Key Features**:
  - Displays a large background image with text and a "Shop Now" button.
  - Includes statistics like "200+ International Brands" and "30,000+ Happy Customers."
  - Fully responsive for different screen sizes.

---

### 5. **Brands.vue**

- **Description**: Displays a list of popular brand names in a horizontal layout.
- **Key Features**:
  - Uses Tailwind CSS for styling.
  - Fully responsive for all screen sizes.

---

### 6. **NewArrivalSection.vue**

- **Description**: Highlights the latest arrivals in the store.
- **Key Features**:
  - Displays a grid of products with images, names, ratings, and prices.
  - Includes a "View All" button for navigation to the full product list.

---

### 7. **TopSelling.vue**

- **Description**: Highlights the top-selling products in the store.
- **Key Features**:
  - Similar to `NewArrivalSection.vue` but focuses on bestsellers.
  - Includes product images, names, ratings, and prices.

---

### 8. **BrowseByDress.vue**

- **Description**: Allows users to browse products by dress style (e.g., Casual, Formal, Party, Gym).
- **Key Features**:
  - Displays categories with background images and titles.
  - Fully responsive for all screen sizes.

---

### 9. **OurHappyCustomer.vue**

- **Description**: Displays customer reviews in a horizontally scrollable section.
- **Key Features**:
  - Uses the `CustomerReview` component to display individual reviews.
  - Horizontal scrolling with hidden scrollbars for a clean design.

---

### 10. **CustomerReview.vue**

- **Description**: A reusable component for displaying individual customer reviews.
- **Key Features**:
  - Includes the customer's name, rating, and review text.
  - Styled with Tailwind CSS for a modern card layout.

---

### 11. **Footer.vue**

- **Description**: The footer section of the homepage.
- **Key Features**:
  - Includes subscription options, social media links, and navigation links.
  - Fully responsive for all screen sizes.

---

### Assets

- All images used in the homepage are stored in the `src/assets/home_view_assets` folder.
- Key images include:
  - `casual_14.png`, `formal_13.png`, `gym_16.png`, `Party_15.png` for `BrowseByDress.vue`.
  - `image_7.png`, `image_9.png`, `image_10.png` for `NewArrivalSection.vue` and `TopSelling.vue`.
  - `Rectangle_2.png`, `Rectangle_3.png` for `HeroSection.vue`.

---

### Styling

- **Tailwind CSS**: The project uses Tailwind CSS for styling, ensuring a responsive and modern design.
- **Custom Fonts**: Fonts like `ABeeZee`, `Anton`, `Playfair Display`, and `Boldonse` are imported and used across components.

---

### Icons

- **Remix Icons**: The project uses `remixicon` for icons like close buttons, arrows, and social media icons.

---

### Notes

- All components are scoped to ensure styles do not leak into other parts of the application.
- The `hide-scrollbar` utility is used in `OurHappyCustomer.vue` to hide horizontal scrollbars while maintaining scroll functionality.

---

## ProductDetailView Page

The `productviewscomponents` folder contains all components related to the product detail page. Below is a detailed explanation of each component and its functionality.

![Product Detail Page](./src/assets/productdetail_assets/Screenshot%202025-05-03%20232643.png)
![Product Detail Page](./src/assets/productdetail_assets/Screenshot%202025-05-03%20232757.png)
![Product Detail Page](./src/assets/productdetail_assets/Screenshot%202025-05-03%20232825.png)
![Product Detail Page](./src/assets/productdetail_assets/Screenshot%202025-05-03%20232844.png)

### 1. **ProductDetailView.vue**

- **Description**: Main container view for the product detail page.
- **Key Components**:
  - `Navbar`: Navigation bar component
  - `ProductDetail`: Main product detail component
  - `Footer`: Footer component

---

### 2. **ProductDetail.vue**

- **Description**: Displays detailed information about a specific product.
- **Key Features**:
  - Product image gallery with thumbnails
  - Product title, rating, and price information
  - Color selection with visual indicators
  - Size selection (S, M, L)
  - Quantity selector with increment/decrement functionality
  - Add to Cart button
  - Tab navigation for additional product information

#### Tab Sections:

1. **Product Details**

   - Displays product specifications and information
   - Shows materials, care instructions, and other details

2. **Ratings & Reviews**

   - Shows overall product rating
   - Displays customer reviews
   - Option to write new reviews

3. **FAQs**
   - Common questions and answers about the product
   - Expandable/collapsible FAQ sections

---

### 3. **ProductReview.vue**

- **Description**: Handles the display and management of product reviews.
- **Key Features**:
  - Shows total review count
  - Filter and sort options
  - Individual review cards with customer feedback
  - "Write a Review" button
  - Load more reviews functionality

---

### 4. **ProductFaq.vue**

- **Description**: Manages frequently asked questions about the product.
- **Key Features**:
  - Collapsible FAQ sections
  - Common questions about shipping, returns, and product care
  - Interactive toggle for answers

---

### 5. **ProductsDetailRating.vue**

- **Description**: Displays detailed rating information.
- **Key Features**:
  - Overall product rating
  - Rating distribution
  - Total number of reviews

---

### Styling

- Uses Tailwind CSS for responsive design
- Custom styling for interactive elements
- Consistent theme with the main application

---

### User Interactions

1. **Image Gallery**:

   - Main product image
   - Thumbnail navigation
   - Image zoom on hover (if applicable)

2. **Product Selection**:

   - Color selection with visual feedback
   - Size selection with button interface
   - Quantity adjustment with +/- controls

3. **Tab Navigation**:
   - Smooth transitions between tabs
   - Active tab indication
   - Responsive layout for mobile views

---

### Notes

- All components use scoped styling to prevent CSS conflicts
- Fully responsive design for mobile and desktop views
- Interactive elements have hover and focus states
- Integrates with the main navigation and footer components

---

## CartView Documentation

The `cartviewcomponents` folder contains components related to the shopping cart functionality. Below is a detailed explanation of each component and its features.

![Cart Page](./src/assets/cartassets/Screenshot%202025-05-04%20190015.png)
![Cart Page](./src/assets/cartassets/Screenshot%202025-05-04%20190035.png)

### 1. **CartView.vue**

- **Description**: Main container view for the shopping cart page.
- **Key Components**:
  - `Navbar`: Navigation bar component
  - `CartDetail`: Main cart detail component
  - `Footer`: Footer component

---

### 2. **CartDetail.vue**

- **Description**: Displays the cart contents and order summary.
- **Key Features**:
  - Cart items list with product details
  - Order summary with pricing breakdown
  - Responsive layout for mobile and desktop views
  - Checkout button with hover effects

#### Order Summary Section:

- Displays subtotal
- Shows discount (if applicable)
- Includes delivery fee
- Calculates total amount
- Checkout button with arrow icon

---

### 3. **CartProduct.vue**

- **Description**: Individual cart item component with product details and controls.
- **Key Features**:
  - Product image display
  - Product name and details
  - Size and color information
  - Quantity adjustment controls
  - Delete item functionality
  - Price information

#### Product Controls:

- **Quantity Adjuster**:
  - Increment/decrement buttons
  - Direct input of quantity
  - Minimum quantity validation
- **Delete Button**:
  - Remove item from cart
  - Visual feedback on hover

---

### Styling

- Uses Tailwind CSS for responsive design
- Custom hover effects on buttons
- Consistent theme with main application
- Responsive layout breakpoints:
  - Mobile: Single column layout
  - Desktop: Two-column layout with cart items and summary side by side

---

### User Interactions

1. **Quantity Management**:

   - Increase/decrease product quantity
   - Direct quantity input
   - Minimum quantity enforcement (cannot go below 1)

2. **Cart Management**:

   - Remove items from cart
   - Update quantities
   - Real-time price updates

3. **Checkout Process**:
   - Clear call-to-action button
   - Hover effects for better user experience
   - Summary of costs before proceeding

---

---

## Categories Products Filter View Documentation

The `categoryviewcomponents` folder contains components related to product filtering and display functionality. Below is a detailed explanation of each component and its features.

![Categories Page](./src/assets/categoriesassets/Screenshot%202025-05-05%20071316.png)
![Categories Page](./src/assets/categoriesassets/Screenshot%202025-05-05%20071345.png)

### 1. **CategoryView.vue**

- **Description**: Main container view for the category browsing page
- **Key Components**:
  - `Navbar`: Main navigation component
  - `FilterProducts`: Filter sidebar component
  - `ProductComponent`: Product card grid
  - `Footer`: Footer component

#### Layout Structure:

```vue
<div class="md:min-h-[90vh] md:flex md:px-20 md:py-10 mt-10 md:gap-10 w-full relative">
  <!-- Filter Section -->
  <div class="md:min-w-[20%]">
    <FilterProducts />
  </div>

  <!-- Products Grid -->
  <div class="md:min-w-[80%]">
    <ProductComponent />
  </div>
</div>
```

#### Code Example:

```vue
<script>
export default {
  name: "CategoryView",
  components: {
    Navbar,
    FilterProducts,
    ProductComponent,
    Footer,
  },
  data() {
    return {
      isFilterVisible: false,
    };
  },
  methods: {
    handleFilterSection() {
      this.isFilterVisible = !this.isFilterVisible;
    },
  },
};
</script>
```
