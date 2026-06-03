[MUSA_LOOM_README.md](https://github.com/user-attachments/files/28549751/MUSA_LOOM_README.md)
# MUSA LOOM — Luxury Women's Fashion Store
### Complete Project Documentation

---

```
███╗   ███╗██╗   ██╗███████╗ █████╗     ██╗      ██████╗  ██████╗ ███╗   ███╗
████╗ ████║██║   ██║██╔════╝██╔══██╗    ██║     ██╔═══██╗██╔═══██╗████╗ ████║
██╔████╔██║██║   ██║███████╗███████║    ██║     ██║   ██║██║   ██║██╔████╔██║
██║╚██╔╝██║██║   ██║╚════██║██╔══██║    ██║     ██║   ██║██║   ██║██║╚██╔╝██║
██║ ╚═╝ ██║╚██████╔╝███████║██║  ██║    ███████╗╚██████╔╝╚██████╔╝██║ ╚═╝ ██║
╚═╝     ╚═╝ ╚═════╝ ╚══════╝╚═╝  ╚═╝    ╚══════╝ ╚═════╝  ╚═════╝ ╚═╝     ╚═╝
```

> **Modern · Classy · Trendy · Luxurious · Feminine**
> A premium women's fashion e-commerce platform with full admin control, Amazon affiliate integration, and affiliate marketing system.

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Brand Identity](#2-brand-identity)
3. [Tech Stack](#3-tech-stack)
4. [File Structure](#4-file-structure)
5. [Getting Started](#5-getting-started)
6. [Admin Dashboard](#6-admin-dashboard)
7. [Product Management](#7-product-management)
8. [Amazon Affiliate System](#8-amazon-affiliate-system)
9. [Category Management](#9-category-management)
10. [Banner Management](#10-banner-management)
11. [Click & Affiliate Analytics](#11-click--affiliate-analytics)
12. [Storefront Features](#12-storefront-features)
13. [Shopping Experience](#13-shopping-experience)
14. [User Authentication](#14-user-authentication)
15. [Affiliate Marketing Program](#15-affiliate-marketing-program)
16. [Dark Mode](#16-dark-mode)
17. [Coupon System](#17-coupon-system)
18. [Product Data Schema](#18-product-data-schema)
19. [Brand Color Palette](#19-brand-color-palette)
20. [Pages & Routes](#20-pages--routes)
21. [Customisation Guide](#21-customisation-guide)
22. [Deployment Guide](#22-deployment-guide)
23. [Frequently Asked Questions](#23-frequently-asked-questions)
24. [Roadmap](#24-roadmap)
25. [License](#25-license)

---

## 1. Project Overview

**MUSA LOOM** is a fully functional, single-file React e-commerce application built for a luxury women's fashion brand. The platform combines a high-end shopping front-end with a comprehensive admin dashboard — all in one self-contained component.

### What It Does

- Presents a curated women's fashion catalogue across 6 product categories
- Allows customers to browse, filter, wish-list, and purchase products
- Enables admins to securely log in and manage every aspect of the store
- Tracks Amazon affiliate link clicks and estimates commission revenue
- Supports a full affiliate marketing program with referral links and earnings dashboards
- Renders beautifully in both light and dark mode with a premium, feminine aesthetic

### Key Numbers

| Metric | Value |
|---|---|
| Total pages / views | 10 |
| Product categories | 6 (expandable) |
| Admin dashboard sections | 7 |
| Sample products pre-loaded | 8 |
| Lines of code | ~1,260 |
| External dependencies | React only |
| External fonts | Google Fonts (Cormorant Garamond) |

---

## 2. Brand Identity

### Design Philosophy

MUSA LOOM is built around four pillars:

| Pillar | Expression |
|---|---|
| **Modern** | Clean layouts, ample whitespace, minimal chrome |
| **Classy** | Serif typography (Cormorant Garamond), restrained colour use |
| **Luxurious** | Gold gradient accents, premium product imagery |
| **Feminine** | Rose-petal tones, soft shadows, elegant micro-interactions |

### Typography

| Role | Font | Weight | Use |
|---|---|---|---|
| Display / Headings | Cormorant Garamond | 300–700 | Hero titles, product names, section headers |
| Body / UI | System sans-serif | 400–700 | Buttons, labels, navigation, prices |
| Accent lettering | Cormorant Garamond Italic | 300 | Pull quotes, hero sub-headings |

### Voice & Tone

- Sophisticated but approachable
- Minimal exclamation points
- Present-tense, confident product descriptions
- British English spellings preferred (colour, jewellery, elegance)

---

## 3. Tech Stack

| Layer | Technology |
|---|---|
| UI Framework | **React 18** (functional components, hooks) |
| State Management | React `useState` (local state, no external store) |
| Styling | Inline styles + CSS-in-JS via `<style>` tag |
| Font | Google Fonts — Cormorant Garamond |
| Image Handling | FileReader API (base64 upload) + Unsplash URLs |
| Routing | Custom page-state router (no React Router needed) |
| Build Tool | Any (Vite, Create React App, Next.js, or Claude Artifact) |
| Deployment | Vercel, Netlify, GitHub Pages, or any static host |

### Why No External Libraries?

The entire store is intentionally built with **zero npm dependencies beyond React**. This means:

- Instant setup — no `npm install` delay
- No version conflicts
- Maximum portability — drop the file into any React project
- Smaller bundle size

---

## 4. File Structure

```
musa-loom-store.jsx          ← Entire application (single file)
MUSA_LOOM_README.md          ← This documentation
```

### Internal Component Architecture

```
MusaLoom()                   ← Root component (all state lives here)
├── AdminLogin               ← Secure admin login gate
├── Nav                      ← Sticky navigation bar
├── HomePage                 ← Hero + categories + featured products
│   ├── BannerSlider         ← Dynamic homepage banners
│   ├── CategoryGrid         ← 6 category cards
│   ├── FeaturedProducts     ← First 8 products
│   └── Newsletter           ← Email capture form
├── ShopPage                 ← Full product catalogue with filters
│   ├── Sidebar filters      ← Category, price range, min rating
│   └── ProductGrid          ← Responsive product cards
├── ProductDetail            ← Full product page
│   ├── ImageGallery         ← Multi-image viewer
│   ├── VariantSelector      ← Colour + size pickers
│   ├── AmazonButton         ← Affiliate link with click tracking
│   ├── AIRecommendations    ← Related products
│   └── ReviewSystem         ← Star rating + written reviews
├── CartPage                 ← Shopping bag + order summary
├── OrderPage                ← Order confirmation + tracking
├── AuthPage                 ← Sign in / Register
├── WishPage                 ← Saved / wish-listed items
├── AffiliatePage            ← Affiliate marketing portal
│   ├── Dashboard            ← Earnings + referral link
│   ├── Leaderboard          ← Top affiliates
│   ├── Register             ← New affiliate application
│   └── Withdraw             ← Earnings withdrawal request
├── AdminDashboard           ← Full admin control centre
│   ├── Overview             ← KPI cards + charts
│   ├── ProductsList         ← Table of all products
│   ├── EditProduct          ← Add / edit product form
│   ├── Categories           ← Category CRUD
│   ├── Banners              ← Homepage banner manager
│   ├── ClickAnalytics       ← Affiliate click tracker
│   └── SalesAnalytics       ← Revenue charts
├── Footer                   ← Links + payment badges
└── PCard                    ← Reusable product card component
```

---

## 5. Getting Started

### Option A — Run in Claude Artifact (Fastest)

1. Open Claude at [claude.ai](https://claude.ai)
2. Paste the contents of `musa-loom-store.jsx` into a message asking to render it
3. The store renders instantly in the Artifact panel — no setup required

### Option B — Local React App (Vite)

```bash
# 1. Create a new Vite + React project
npm create vite@latest musa-loom -- --template react
cd musa-loom

# 2. Replace the default App component
cp musa-loom-store.jsx src/App.jsx

# 3. Update src/main.jsx to import App
# (default Vite setup already does this)

# 4. Install and run
npm install
npm run dev
```

### Option C — Next.js

```bash
# 1. Create Next.js app
npx create-next-app@latest musa-loom
cd musa-loom

# 2. Create a client component
# Add "use client" directive at the top of musa-loom-store.jsx

# 3. Import in app/page.tsx
# import MusaLoom from '../musa-loom-store'
# export default MusaLoom

npm run dev
```

### Option D — CodeSandbox / StackBlitz

1. Go to [codesandbox.io](https://codesandbox.io) or [stackblitz.com](https://stackblitz.com)
2. Create a new React sandbox
3. Paste `musa-loom-store.jsx` as `App.jsx`
4. Live preview appears instantly

---

## 6. Admin Dashboard

### Accessing the Admin Panel

Navigate to the **ADMIN** link in the top navigation bar.

You will be presented with a secure, full-screen login page styled in the MUSA LOOM obsidian brand theme.

### Default Admin Credentials

```
Email:    admin@musaloom.com
Password: MusaLoom2026!
```

> **Security Note:** These are demo credentials embedded in the front-end. For a production deployment, replace this with a real authentication system (JWT, OAuth, Supabase Auth, Firebase Auth, etc.).

### Changing Admin Credentials

Find and update this constant near the top of the file:

```jsx
const ADMIN_CREDS = {
  email:    "admin@musaloom.com",
  password: "MusaLoom2026!"
};
```

### Admin Sidebar Navigation

| Section | Icon | Description |
|---|---|---|
| Dashboard | ◈ | Overview KPIs, top products, category breakdown |
| Products | ▦ | Full product table with edit / delete |
| Add Product | ✦ | New product form with image upload |
| Categories | ◉ | Add, edit, delete categories |
| Banners | ▣ | Homepage banner manager |
| Click Analytics | ⬡ | Amazon affiliate click tracking |
| Sales Analytics | ◐ | Revenue charts and traffic overview |

---

## 7. Product Management

### Adding a New Product

1. Click **ADMIN** in the navigation
2. Log in with admin credentials
3. Click **Add Product** (✦) in the sidebar
4. Fill in the product form (see fields below)
5. Click **Add Product**

### Editing an Existing Product

1. Go to **Products** (▦) in the sidebar
2. Find the product in the table
3. Click the **Edit** button
4. Update any fields
5. Click **Update Product**

### Deleting a Product

1. Go to **Products** (▦) in the sidebar
2. Click the **Delete** button on the product row
3. The product is removed immediately

### Product Form Fields

| Field | Type | Required | Description |
|---|---|---|---|
| Product Name | Text | ✅ Yes | Display name of the product |
| Price ($) | Number | ✅ Yes | Original / RRP price |
| Sale Price ($) | Number | ✅ Yes | Discounted selling price |
| Stock Quantity | Number | ✅ Yes | Available units in stock |
| Category | Dropdown | ✅ Yes | One of the 6 categories |
| Badge | Dropdown | No | New / Best Seller / Sale / Trending / Luxury |
| Sizes | Text | ✅ Yes | Comma-separated e.g. `XS,S,M,L,XL` |
| Colours | Text | ✅ Yes | Comma-separated hex codes e.g. `#c9a96e,#fff` |
| Description | Textarea | ✅ Yes | Product description (shown on product page) |
| Product Image | File Upload | Recommended | Upload JPG/PNG/WebP from your device |
| Image URL | Text | Alternative | Paste an external image URL |
| Amazon Link | Text | No | Full Amazon product URL with affiliate tag |

### Image Upload

The image upload uses the browser's **FileReader API** to convert uploaded images to base64. This means:

- No server or storage backend required for demo purposes
- Images are stored in React state (lost on page refresh in demo mode)
- For production: integrate with Cloudinary, AWS S3, Supabase Storage, or Firebase Storage

**Supported formats:** JPG · PNG · WebP · GIF  
**Recommended size:** At least 800×1000px, portrait orientation  
**Max file size:** 5MB (browser limit)

---

## 8. Amazon Affiliate System

### How It Works

1. Admin adds an Amazon product URL to any product (with affiliate tag)
2. The product card displays an orange **Amazon** badge
3. On the product detail page, a prominent **Also Available on Amazon** button appears
4. Every click on that button is tracked and recorded in the admin analytics
5. Revenue estimates are calculated at a default 4% commission rate

### Adding Your Amazon Associate Tag

Your Amazon affiliate link format should be:

```
https://www.amazon.com/dp/PRODUCT_ID/?tag=YOUR-ASSOCIATE-TAG-20
```

Example:
```
https://www.amazon.com/dp/B08XYZ123/?tag=musaloom-20
```

Replace `musaloom-20` with your actual Amazon Associates tag.

### Setting Up Amazon Associates

1. Visit [Amazon Associates](https://affiliate-program.amazon.com)
2. Sign up or log in to your account
3. Search for the product you want to link
4. Click **Get Link** and copy the URL
5. Paste the full URL into the **Amazon Link** field when adding/editing a product

### Click Tracking

Every Amazon affiliate link click is tracked in two places:

| Location | Tracked Field | Description |
|---|---|---|
| Product card | `affiliateClicks` | Increments each time Amazon button is clicked |
| Product page | `affiliateClicks` | Same tracker on the detail page |
| Admin → Click Analytics | Dashboard view | Shows all products with click counts |

### Commission Estimation

The Click Analytics dashboard estimates revenue using:

```
Estimated Revenue = Affiliate Clicks × Sale Price × 4%
```

This is a rough estimate. Actual commissions depend on product category and Amazon's current commission rates.

---

## 9. Category Management

### Default Categories

| ID | Name | Icon | Description |
|---|---|---|---|
| `dresses` | Dresses | 👗 | Elegant & Chic |
| `tops` | Tops | 👚 | Casual & Trendy |
| `nails` | Nails | 💅 | Nail Art & Polish |
| `shoes` | Shoes | 👠 | Heels & Flats |
| `jewelry` | Jewelry | 💍 | Fine Jewelry |
| `glasses` | Glasses | 🕶️ | Frames & Sunnies |

### Adding a New Category

1. Go to **ADMIN → Categories (◉)**
2. Click **+ Add Category**
3. Fill in Name, Icon (any emoji), and Description
4. Click **Save**

The new category immediately appears in:
- The homepage category grid
- The shop page sidebar filter
- The admin product form category dropdown

### Editing a Category

1. Click **Edit** on any category card
2. Update Name, Icon, or Description
3. Click **Save**

### Deleting a Category

1. Click **Delete** on the category card
2. The category is removed from navigation
3. **Note:** Existing products with that category ID are not automatically re-assigned — update them manually

---

## 10. Banner Management

### What Are Banners?

Homepage hero banners are the full-width promotional sections displayed at the top of the home page. They rotate automatically when multiple active banners exist.

### Default Banners

| Title | Subtitle | Background |
|---|---|---|
| New Arrivals | Spring / Summer 2026 | Rose petal gradient |
| Up to 40% Off | Limited time sale | Champagne gold gradient |

### Adding a Banner

1. Go to **ADMIN → Banners (▣)**
2. Click **+ Add Banner**
3. Fill in:
   - **Title** — Main hero headline
   - **Subtitle** — Supporting text / tagline
   - **CTA Button Text** — e.g. Shop Now, View Collection
   - **Link URL** — Where the CTA button points
   - **Background** — CSS gradient string (preview shown live)
4. Click **Save Banner**

### CSS Gradient Examples for Banners

```css
/* Rose Blush */
linear-gradient(135deg, #f9eff2, #f0d4dc)

/* Champagne Gold */
linear-gradient(135deg, #f7f0e6, #e8d5a3)

/* Midnight Luxury */
linear-gradient(135deg, #1a1018, #2d1f28)

/* Sage Green */
linear-gradient(135deg, #d4e0d0, #e8f3e8)

/* Dusty Mauve */
linear-gradient(135deg, #e8d0da, #d4a0b5)
```

### Toggling Banner Visibility

Click the **● Active / ○ Hidden** toggle button on any banner to show or hide it without deleting it.

### Deleting a Banner

Click **Delete** on the banner row. This is immediate and irreversible.

---

## 11. Click & Affiliate Analytics

### Accessing Analytics

Go to **ADMIN → Click Analytics (⬡)**

### Metrics Displayed

| Metric | Description |
|---|---|
| Total Affiliate Clicks | Sum of all Amazon link clicks across all products |
| Products with Amazon Links | Count of products that have an affiliate URL set |
| Est. Commissions | Projected earnings at 4% commission rate |

### Per-Product Click Table

For each product the table shows:

| Column | Description |
|---|---|
| Product | Name of the product |
| Category | Product category badge |
| Sale Price | Current selling price |
| Amazon Link | Clickable "View Link ↗" if set, or "—" |
| Page Clicks | Times the product card was interacted with |
| Affiliate Clicks | Times the Amazon button was clicked (with visual bar) |
| Est. Revenue | `Affiliate Clicks × Sale Price × 4%` |

### Sales Analytics

Go to **ADMIN → Sales Analytics (◐)**

Displays:
- **Monthly Revenue Bar Chart** — 12 months visualised with animated bars
- **Top Revenue Products** — Ranked by estimated revenue (reviews × price × 5%)
- **Traffic Overview** — Breakdown of traffic sources with percentage bars:
  - Organic Search: 48%
  - Social Media: 31%
  - Direct: 14%
  - Affiliate: 7%

---

## 12. Storefront Features

### Homepage

| Section | Description |
|---|---|
| Announcement Bar | Scrolling promotion with coupon code |
| Hero Banner Slider | Dynamic banners with dot navigation |
| Stats Bar | Customer count, brand count, shipping, returns |
| Category Grid | 6 animated category cards |
| Featured Collection | First 8 products |
| Amazon Affiliate Strip | Quick links to Amazon-listed products |
| Newsletter Signup | Email capture with validation |
| Social Media Links | Instagram, TikTok, Pinterest, YouTube |

### Shop Page

| Feature | Description |
|---|---|
| Category Sidebar | Filter by all 6 categories |
| Price Range Filter | Min and max price inputs |
| Rating Filter | 4 rating tiers (All / 3★+ / 4★+ / 4.5★+) |
| Sort Options | Featured / Price Low-High / Price High-Low / Top Rated |
| Live Product Count | Updates dynamically as filters change |
| Empty State | Clear filters button when no results match |

### Product Detail Page

| Section | Description |
|---|---|
| Image Gallery | 3-image viewer with thumbnail selector |
| Colour Picker | Visual swatch selector with ring highlight |
| Size Selector | Toggle buttons for all sizes |
| Quantity Selector | +/− counter |
| Stock Badge | Green "In Stock (n left)" or red "Out of Stock" |
| Add to Cart | Adds selected variant to cart |
| Wishlist | Heart toggle with instant feedback |
| Amazon Button | Prominent CTA with click tracking (only shown if link set) |
| Trust Badges | Shipping / Returns / Secure checkout |
| AI Recommendations | 4 related products |
| Review System | Star rating display + write review form |

---

## 13. Shopping Experience

### Cart / Shopping Bag

- View all items with image, name, colour swatch, size
- Adjust quantity with +/− controls
- Remove individual items
- Apply coupon codes
- View order summary with subtotal, discount, shipping, total
- Multiple payment method badges displayed
- One-click secure checkout

### Order Confirmation

After checkout the customer sees:
- Order number (e.g. `#MUSALOOM-47382`)
- Estimated delivery window
- Visual 4-step order progress tracker (Placed → Processing → Shipped → Delivered)

### Wishlist

- Save products with the heart (♡) icon on any card
- Wishlist count badge on nav icon
- Full wishlist page with same product cards
- Remove by clicking heart again

### Search

- Live search bar in navigation
- Searches product name and description simultaneously
- Automatically switches to Shop page when query is entered

---

## 14. User Authentication

### Customer Registration

1. Click **Sign In** in the navigation
2. Toggle to **Register**
3. Enter Full Name, Email, and Password
4. Click **Create Account →**

### Customer Login

1. Click **Sign In** in the navigation
2. Enter Email and Password
3. Click **Sign In →**

### Signed-In State

When signed in, the navigation shows `Hi, [First Name]` instead of "Sign In".

### Sign Out

Available on the Auth page when already logged in.

> **Note:** The current auth system is front-end only (no backend). For production, integrate with Supabase Auth, Firebase Auth, Auth0, or Next.js Auth.

---

## 15. Affiliate Marketing Program

Navigate to **AFFILIATE** in the top navigation.

### Affiliate Dashboard

Displays summary cards for:
- **Total Earned** — Lifetime commission earnings
- **Referral Sales** — Number of sales attributed to the affiliate
- **Commission Rate** — Current tier percentage

Also shows the affiliate's unique referral link with a copy button and social share buttons (Instagram, TikTok, Pinterest, WhatsApp).

### Commission Tiers

| Tier | Rate | Requirement |
|---|---|---|
| Standard | 10% | Default for all new affiliates |
| Silver | 15% | 20+ referred sales |
| Gold | 20% | 50+ referred sales |

### Leaderboard

Top 3 affiliates shown with:
- Rank badge
- Name
- Number of sales
- Total earnings

### Affiliate Registration

New affiliates can apply by filling in:
- Full Name
- Email address
- Website or Social Media Handle
- Preferred commission tier

Applications are reviewed within 48 hours.

### Withdrawal Requests

Affiliates can request earnings withdrawal by:
- Entering the withdrawal amount
- Selecting payment method (PayPal or Bank Transfer)
- Entering account details

Minimum withdrawal: $50  
Processing time: 3–5 business days

---

## 16. Dark Mode

Click the **🌙 / ☀️** icon in the navigation bar to toggle between light and dark mode.

### Light Mode Colours

| Element | Colour |
|---|---|
| Background | `#fdfaf6` (Ivory) |
| Surface | `#ffffff` |
| Surface Alt | `#f5f0e8` (Cream) |
| Text | `#1a1018` (Obsidian) |
| Muted Text | `#5c4a56` (Slate) |
| Border | `rgba(26,16,24,0.08)` |

### Dark Mode Colours

| Element | Colour |
|---|---|
| Background | `#100c10` |
| Surface | `#1c1520` |
| Surface Alt | `#241a22` |
| Text | `#f5eff2` |
| Muted Text | `#9e8fa0` |
| Border | `rgba(255,255,255,0.07)` |

Both modes use the same gold gradient accent `#c9a96e → #e8d5a3 → #c9a96e` for consistency.

---

## 17. Coupon System

### Available Coupon

| Code | Discount | Status |
|---|---|---|
| `MUSALOOM40` | 40% off entire order | Active |

### Applying a Coupon

1. Add items to cart
2. Go to the Cart page
3. Type the coupon code in the input field
4. Click **Apply**
5. The discount is shown in the order summary

### Adding More Coupons

Find this section in the `CartPage` component:

```jsx
if (coupon.toUpperCase() === "MUSALOOM40") {
  setCouponOk(true);
  notify("✓ 40% discount applied!");
} else {
  notify("Invalid coupon", "err");
}
```

Add more conditions:

```jsx
if (coupon.toUpperCase() === "MUSALOOM40") {
  setCouponOk(true); // 40% off
} else if (coupon.toUpperCase() === "WELCOME15") {
  setCoupon15(true); // add a new state for 15% off
} else {
  notify("Invalid coupon", "err");
}
```

---

## 18. Product Data Schema

Each product follows this data structure:

```javascript
{
  id:             Number,    // Unique identifier (auto-generated via Date.now())
  name:           String,    // e.g. "Midnight Velvet Gown"
  category:       String,    // e.g. "dresses" — must match a category ID
  price:          Number,    // Original price in USD e.g. 289
  salePrice:      Number,    // Discounted price in USD e.g. 199
  stock:          Number,    // Units available e.g. 12
  sizes:          Array,     // e.g. ["XS","S","M","L","XL"]
  colors:         Array,     // Hex codes e.g. ["#1a1a2e","#c9a96e"]
  image:          String,    // URL or base64 data string
  badge:          String,    // "New" | "Best Seller" | "Sale" | "Trending" | "Luxury" | ""
  description:    String,    // Product description paragraph
  amazonLink:     String,    // Full Amazon affiliate URL or ""
  rating:         Number,    // e.g. 4.8 (0–5)
  reviews:        Number,    // Review count e.g. 124
  clicks:         Number,    // Page interaction count (auto-tracked)
  affiliateClicks:Number,    // Amazon link click count (auto-tracked)
}
```

---

## 19. Brand Color Palette

```javascript
const C = {
  // Rose Family
  rosePetal:  "#f9eff2",   // Lightest pink — page backgrounds
  roseLight:  "#f0d4dc",   // Soft rose — cards, banners
  roseMid:    "#d4879a",   // Mid rose — chart fills
  roseDark:   "#9b4f6a",   // Deep rose — accent text

  // Gold Family
  champagne:  "#f7f0e6",   // Warm off-white
  gold:       "#c9a96e",   // Primary gold — buttons, accents
  goldDeep:   "#a8783a",   // Deep gold — hover states
  goldLight:  "#e8d5a3",   // Light gold — gradient midpoint

  // Neutral Base
  ivory:      "#fdfaf6",   // Main light background
  cream:      "#f5f0e8",   // Section alt background

  // Dark Base
  obsidian:   "#1a1018",   // Primary dark — text, dark surfaces
  charcoal:   "#2d1f28",   // Secondary dark
  slate:      "#5c4a56",   // Muted text

  // Accent
  blush:      "#e8b4c0",   // Soft blush
  dustyRose:  "#c4788a",   // Dusty rose
  sage:       "#d4e0d0",   // Sage green
  mint:       "#e8f3e8",   // Mint
};

// Gradient definitions
const GOLD_GRAD = "linear-gradient(135deg, #c9a96e, #e8d5a3, #c9a96e)";
const ROSE_GRAD = "linear-gradient(135deg, #f0d4dc, #f9eff2)";
```

---

## 20. Pages & Routes

The app uses a single-state router (`page` state variable). Available page values:

| Page State | URL Equivalent | Component |
|---|---|---|
| `"home"` | `/` | `HomePage` |
| `"shop"` | `/shop` | `ShopPage` |
| `"product"` | `/product/:id` | `ProductDetail` |
| `"cart"` | `/cart` | `CartPage` |
| `"order"` | `/order/confirmation` | `OrderPage` |
| `"auth"` | `/account` | `AuthPage` |
| `"wishlist"` | `/wishlist` | `WishPage` |
| `"affiliate"` | `/affiliate` | `AffiliatePage` |
| `"admin"` | `/admin` | `AdminLogin` → `AdminDashboard` |

### Navigation Function

```javascript
const goto = (page, category = "all") => {
  setPage(page);
  if (page === "shop") setActiveCat(category);
};
```

---

## 21. Customisation Guide

### Change the Brand Name

Search and replace all instances of `MUSA LOOM` in the file:

```bash
sed -i 's/MUSA LOOM/YOUR BRAND NAME/g' musa-loom-store.jsx
```

### Change Admin Credentials

```javascript
// Line ~41 in the file
const ADMIN_CREDS = {
  email:    "your-admin@yourdomain.com",
  password: "YourSecurePassword2026!"
};
```

### Change the Gold Accent Colour

```javascript
// Find and replace the gold hex value
gold: "#c9a96e"  →  gold: "#YOUR_HEX"
```

Also update:
```javascript
const GOLD_GRAD = `linear-gradient(135deg, #YOUR_HEX, #LIGHT_VERSION, #YOUR_HEX)`;
```

### Add More Product Categories

```javascript
const INIT_CATS = [
  // existing categories...
  { id: "bags", name: "Bags", icon: "👜", desc: "Handbags & Clutches" },
];
```

### Change Commission Rate

Search for `0.04` in the file — this is the 4% estimate used in the analytics dashboard:

```javascript
// Change to your actual average commission rate
const EST_COMMISSION_RATE = 0.04; // 4%
```

### Add More Coupon Codes

In the `CartPage` component:

```javascript
if (coupon.toUpperCase() === "MUSALOOM40") {
  setCouponOk(true); notify("✓ 40% discount applied!");
} else if (coupon.toUpperCase() === "WELCOME10") {
  // add logic for 10% off
} else {
  notify("Invalid coupon", "err");
}
```

### Update Sample Products

Edit `INIT_PRODUCTS` at the top of the file. Each product must follow the schema defined in [Section 18](#18-product-data-schema).

---

## 22. Deployment Guide

### Vercel (Recommended)

```bash
# 1. Push your project to GitHub
git init && git add . && git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/musa-loom.git
git push -u origin main

# 2. Import project at vercel.com
# 3. Select framework: Vite or Create React App
# 4. Deploy — automatic HTTPS + CDN included
```

### Netlify

```bash
# Build the project
npm run build

# Drag the /dist or /build folder to netlify.com/drop
# Or connect your GitHub repo for auto-deployments
```

### GitHub Pages (with Vite)

```javascript
// vite.config.js
export default {
  base: '/musa-loom/',  // your repo name
}
```

```bash
npm run build
npx gh-pages -d dist
```

### Self-Hosted (Nginx)

```bash
npm run build
# Copy /dist contents to your web server root
# Configure Nginx to serve index.html for all routes
```

```nginx
server {
    listen 80;
    server_name musaloom.com;
    root /var/www/musa-loom/dist;
    index index.html;
    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

---

## 23. Frequently Asked Questions

**Q: Is this a full e-commerce backend or just a front-end?**  
A: This is a complete front-end demo. All data lives in React state (resets on page refresh). For production, you need to connect a backend for products, orders, users, and payments.

**Q: How do I connect a real database?**  
A: Replace the `useState` product/category/banner state with API calls. Recommended options: Supabase (free tier), Firebase Firestore, PlanetScale, or a custom Node.js/Express API.

**Q: How do I add real payments?**  
A: Integrate Stripe Checkout or Stripe Elements. The checkout button in `CartPage` can be replaced with a Stripe `loadStripe()` call.

**Q: Can I use this for a real Amazon affiliate store?**  
A: Yes. Add your Amazon Associates tag to all product links. The click tracking is already built in. Ensure you comply with Amazon's affiliate program guidelines (disclosure requirements, link formatting rules).

**Q: Do uploaded images persist after refresh?**  
A: No. Images uploaded via the admin panel are stored as base64 in React state. For persistence, integrate Cloudinary, Firebase Storage, or AWS S3 and store the returned URL in your database.

**Q: Can I add more than 6 categories?**  
A: Absolutely. Add entries to `INIT_CATS` and the admin category manager will handle the rest automatically.

**Q: Is the affiliate commission calculation automatic?**  
A: The dashboard shows estimates based on click tracking. Actual commissions are paid directly by Amazon through their Associates program — no backend processing is needed.

**Q: How do I customise the font?**  
A: Replace the Google Fonts import URL in the `<style>` tag. Change the `fontFamily` values in the `S` style object. Recommended luxury alternatives: Playfair Display, EB Garamond, Libre Baskerville.

---

## 24. Roadmap

### Version 2.0 (Planned)

- [ ] Backend integration (Supabase or Firebase)
- [ ] Persistent user accounts with order history
- [ ] Stripe payment processing
- [ ] Email confirmation system (SendGrid / Resend)
- [ ] Cloudinary image upload integration
- [ ] Multi-language support (Arabic, French, Spanish)
- [ ] Size guide modal per category
- [ ] Product variant inventory tracking
- [ ] Admin bulk product import (CSV)
- [ ] Abandoned cart email reminders

### Version 2.5 (Future)

- [ ] AI-powered outfit builder
- [ ] Virtual try-on (AR integration)
- [ ] Live chat widget
- [ ] Loyalty points system
- [ ] Multi-currency support
- [ ] Mobile app (React Native)

---

## 25. License

```
MIT License

Copyright (c) 2026 MUSA LOOM

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

## Quick Reference Card

```
┌─────────────────────────────────────────────────────────────┐
│                    MUSA LOOM QUICK REFERENCE                │
├─────────────────────────────────────────────────────────────┤
│  ADMIN LOGIN                                                │
│  Email:     admin@musaloom.com                              │
│  Password:  MusaLoom2026!                                   │
├─────────────────────────────────────────────────────────────┤
│  COUPON CODE                                                │
│  MUSALOOM40  →  40% off entire order                        │
├─────────────────────────────────────────────────────────────┤
│  FREE SHIPPING                                              │
│  On all orders over $150                                    │
├─────────────────────────────────────────────────────────────┤
│  AFFILIATE TIERS                                            │
│  Standard  →  10%   (default)                               │
│  Silver    →  15%   (20+ sales)                             │
│  Gold      →  20%   (50+ sales)                             │
├─────────────────────────────────────────────────────────────┤
│  AMAZON COMMISSION ESTIMATE                                 │
│  Tracked at 4% of sale price per affiliate click            │
├─────────────────────────────────────────────────────────────┤
│  BRAND GOLD:  #c9a96e                                       │
│  BRAND DARK:  #1a1018                                       │
│  BRAND ROSE:  #f9eff2                                       │
└─────────────────────────────────────────────────────────────┘
```

---

*Built with ♡ for MUSA LOOM · 2026*
