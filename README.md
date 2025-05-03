# Ecommerce-Frontend-vue-Anubhav

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

*****************************************************************************************
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

*****************************************************************************************
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