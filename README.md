# Africart - Modern E-Commerce Platform

Africart is a contemporary e-commerce web application focused on providing a seamless shopping experience for tech products and accessories. The platform features dynamic product loading, category filtering, a persistent cart system, and a multi-step checkout flow.

## Project Structure

### HTML Files
- **index.html**: The landing page featuring hero sections, value propositions, and a "Featured Products" display.
- **products.html**: The main store page with a sidebar for category filtering, price range adjustment, and sorting.
- **cart.html**: A dedicated full-page cart to view selected items, adjust quantities, and see a subtotal summary.
- **checkout.html**: The final order page comprising contact information, shipping details, and a dynamic order summary.
- **auth.html**: User authentication page (Sign In/Sign Up).

### CSS Styling
- **styles.css**: Universal design tokens, core layout (Flexbox/Grid), navigation header, and main shared components.
- **products.css**: Specific layouts for the sidebar and the grid system used in the product display.
- **checkout.css**: Styles for the two-column checkout layout and form inputs.
- **auth.css**: Design for the authentication interface.

### Logical Core
- **script.js**: The primary engine for the application's interactivity.
- **products.json**: A local data repository containing dummy product information (ID, name, price, rating, stock, category).

## Key JavaScript Logic

The `script.js` file is designed to be **page-aware**, only initializing logic relevant to the current page.

### 1. Persistent Cart System
Uses `localStorage` to ensure your items remain in the cart even after closing the browser.
- `addToCart(product)`: Adds an item or increments the quantity if it already exists.
- `saveCart()`: Keeps the `localStorage` in sync with the current state.
- `updateCartNav()`: Dynamically updates the red counter badge on the navigation bar.

### 2. Dynamic Product Engine
- `fetchProducts()`: Asynchronous function that loads products from `products.json`.
- `renderProducts()`: Generates product cards with images, prices, ratings, and "Add to Cart" buttons.
- `applyFilters()`: Handles real-time filtering by category, price range, and custom sorting (price high-to-low, name, etc.).

### 3. Navigation & Responsiveness
- Implements a hamburger menu for mobile devices.
- Synchronized header logic across all HTML files for a consistent UX.

### 4. Order Processing
- `renderCheckoutSummary()`: Fetches items from the saved cart and calculates tax (16%) and the final total for the checkout page.
- Successful order submission triggers a custom modal popup and redirects the user back to the store.

## Important CSS Classes & IDs

| Element | Description |
| --- | --- |
| `.product-card` | The primary styling for individual product displays. |
| `.category-btn` | Buttons in the sidebar used for product filtering. |
| `#products-container` | The dynamic HTML target where items are rendered via JS. |
| `.header-left` / `.header-right` | Flex containers for the unified responsive navigation. |
| `.cart-item-row` | Styling for a single row item in the full-page cart. |
| `.summary-child` | Items displayed within the order summary (Cart & Checkout). |

## How to Run
Simply open `index.html` in any modern web browser. All logic is handled via client-side JavaScript.
