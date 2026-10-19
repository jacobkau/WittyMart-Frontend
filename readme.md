# WittyMart Project Documentation

## Project Overview

**WittyMart** is a smart shopping platform designed to provide users with a seamless and enjoyable online shopping experience. The platform offers a wide range of products across various categories, including electronics, fashion, home & living, beauty & health, sports & outdoors, and more.

>  **This repository is the frontend only.** It is a static website built with **HTML, CSS, and JavaScript**. There is no backend in this repository. The full product — with user accounts, cart persistence, orders, and admin tools — is a separate **frontend + backend** system hosted in its own repository and served from its own domain.

---

## Table of Contents

1. What This Repository Is (and Isn't)
2. Features (This Frontend)
3. Project Structure
4. Technologies Used
5. Setup Instructions
6. File Descriptions
7. Key Functionalities
8. The Full System (Frontend + Backend)
9. Future Enhancements
10. Credits and License

---

## 1. What This Repository Is (and Isn't)

### What this repository IS
- A **static frontend website**
- Written entirely in **HTML5, CSS3, and vanilla JavaScript**
- Deployable to any static host (Netlify, Vercel, GitHub Pages, Render static site, S3, etc.)
- Demonstrates layout, design, navigation, dark mode, product browsing UI, and a client-side cart
- Fully responsive — works on mobile, tablet, and desktop
- No server, no database, no authentication required to view

### What this repository IS NOT
- **Not a full-stack application**
- **No backend** — no API, no database, no server-side logic
- **No real authentication** — the login and registration forms here are UI-only
- **No persistent cart** — the cart state lives in browser memory / localStorage only
- **No order processing or payment flow**
- **Not the production system**

If you're looking for the production build — with real user accounts, a working cart, order history, and an admin panel — that lives in the **separate full-stack repository** described in section 8.

---

## 2. Features (This Frontend)

- **Responsive Design** — Optimized for desktop, tablet, and mobile
- **Product Categories** — Organized categories for easy navigation
- **Product Browsing** — Browse products, view details, add to cart UI
- **Client-Side Shopping Cart** — Add/remove products, view total cost (stored locally)
- **Dark Mode** — Toggle between light and dark themes (persisted in localStorage)
- **Dynamic Navigation** — Sidebar and navigation bar for easy page access
- **Form UI** — Registration, login, and contact forms (visual only, no submission)
- **Newsletter Subscription UI** — Subscribe prompt with client-side validation
- **Category Filtering** — Browse by category through `breadcrumbs.html`
- **Google Maps Embed** — Displays location on the contact page
- **Footer Links** — Quick access to Terms, Privacy Policy, and Contact

---

## 3. Project Structure

```
Root Directory
│
├── index.html          # Homepage
├── welcome.html        # Welcome page after login (UI demo)
├── home.html           # Registration/Login page (UI only)
├── shop.html           # Shop page with product listings
├── cart.html           # Shopping cart page (client-side)
├── about.html          # About Us page
├── contact.html        # Contact Us page
├── terms.html          # Terms and Policies page
├── breadcrumbs.html    # Category-specific product listings
│
├── style.css           # Main stylesheet
├── script.js           # JavaScript for interactivity
│
├── images/             # Directory for images
│
└── README.md           # Project documentation (this file)
```

---

## 4. Technologies Used

| Layer | Technology | Purpose |
|-------|------------|---------|
| **HTML** | HTML5 | Semantic page structure |
| **CSS** | CSS3 | Styling, responsive layout, dark mode, animations |
| **JavaScript** | Vanilla ES6+ | Interactivity, cart state, theme toggle, form validation |
| **Icons** | Font Awesome 6 | Navigation, buttons, product icons |
| **Fonts** | Google Fonts | Typography |
| **Maps** | Google Maps Embed API | Location on the contact page |

**No frameworks. No build tools. No backend.** Just the three web fundamentals.

---

## 5. Setup Instructions

### Option A — View the Live Demo

Open the deployed site in any modern browser:

🔗 **[https://wittymart.netlify.app/](https://wittymart.netlify.app/)**

### Option B — Run Locally

1. **Download or clone the project**

   ```bash
   git clone <your-repo-url>
   cd wittymart-frontend
   ```

2. **Open `index.html` in a browser**

   - Double-click `index.html` — it will open directly. No server required.
   - Or use a lightweight server for cleaner relative paths:

   ```bash
   # Python 3
   python -m http.server 8000

   # Node.js (if installed)
   npx serve .
   ```

   Then visit `http://localhost:8000`.

3. **Edit files**

   Open the folder in VS Code, Sublime, or any editor. Changes to HTML/CSS/JS reflect immediately on refresh.

### Option C — Deploy to a Static Host

Because this is a pure static site, you can deploy to:

- **Netlify** — drag the folder into Netlify Drop
- **Vercel** — `vercel deploy` from the project root
- **GitHub Pages** — push to a repo, enable Pages on the `main` branch
- **Render** — create a "Static Site" service pointing at the repo
- **Cloudflare Pages** — connect the repo, build command empty, publish directory `./`

---

## 6. File Descriptions

### HTML Files

| File | Description |
|------|-------------|
| `index.html` | Homepage — hero banner, featured products, categories |
| `welcome.html` | Welcome screen shown after login (UI demo, not tied to a real session) |
| `home.html` | Registration and login forms (UI only — no backend submission) |
| `shop.html` | Product listing page with filtering and add-to-cart |
| `cart.html` | Client-side cart — items, quantities, subtotal |
| `about.html` | Mission, story, and team information |
| `contact.html` | Contact form (UI) + embedded Google Maps |
| `terms.html` | Privacy policy, terms & conditions, return policy |
| `breadcrumbs.html` | Category-specific product view with breadcrumb navigation |

### CSS

| File | Description |
|------|-------------|
| `style.css` | Global styles, responsive breakpoints, dark mode variables, animations, component styles |

### JavaScript

| File | Description |
|------|-------------|
| `script.js` | Theme toggle, sidebar navigation, form validation, cart state (localStorage), dynamic updates |

### Images

`images/` contains:
- Product thumbnails and detail images
- Hero and promotional banners
- Site logo and favicon

---

## 7. Key Functionalities

### 1. Product Browsing *(frontend UI)*
Products are hardcoded in the HTML / rendered by JS. Categories are organized for easy navigation. No database lookup — the catalog is static.

### 2. Shopping Cart *(client-side only)*
- Add items to cart via the "Add to Cart" button
- Cart state stored in `localStorage`
- Cart page (`cart.html`) calculates subtotal from the items in storage
- **No order submission** — nothing is sent to a server

### 3. User Authentication *(UI only)*
- Registration and login forms exist on `home.html`
- **No real authentication** — no credentials are sent anywhere
- Redirects to `welcome.html` are simulated for demo purposes
- Real authentication is handled by the full-stack system (see section 8)

### 4. Responsive Design
- Breakpoints at 1024px, 768px, and 480px
- Mobile-first navigation with a slide-out sidebar
- Fluid typography and image sizing

### 5. Dark Mode
- Toggle button in the header
- Preference persisted in `localStorage`
- All colors driven by CSS variables → instant theme switch

### 6. Form Validation *(client-side)*
- HTML5 `required`, `type="email"`, `pattern` attributes
- Additional JS checks (password length, matching confirmation, etc.)
- **No submission** — forms prevent default and show a demo message

### 7. Contact Form *(UI)*
- Displays all required fields with client-side validation
- Embedded Google Map for location
- **No email is sent** — this is a frontend demo only

### 8. Footer Links
- Quick access to Terms, Privacy Policy, and Contact pages

---

## 8. The Full System (Frontend + Backend)

The complete **WittyMart** platform — with the actual production frontend **plus** its backend — lives in a **separate repository** and is served from its own **separate domain**.

### What the full-stack system includes
- **User accounts** — real registration, login, password reset, email verification
- **Persistent cart** — cart synchronized across devices via the database
- **Order history** — view past orders, statuses, tracking
- **Real checkout flow** — address, payment integration, order confirmation
- **Backend API** — REST endpoints for products, users, carts, orders
- **Admin dashboard** — manage products, orders, users, and analytics
- **Database** — users, products, orders, inventory, categories
- **Email notifications** — order confirmations, shipping updates

### Where to find it
- **Repository:** *[link to the full-stack repo](https://github.com/jacobkau/WittyMart-Fronted-and-Backend)*
- **Live domain:** *[link to the production domain](https://wittymart.onrender.com/)*
- **Tech stack:** *PHP + MySQL, Aiven DBMS.*

### What this repository's role is in that system
This frontend can be:
- A **demo** of the UI before a user signs up
- A **landing page** that links into the full app
- A **design reference** for the full-stack frontend

It is **not** the actual frontend that talks to the backend — that lives in the full-stack repo, colocated with its backend for simplicity.

---

## 9. Future Enhancements

Planned for the **full-stack system** (not this static repo):

- Order tracking with real-time status
- Wishlist / favourites synced across devices
- Full-text product search
- Product reviews and ratings
- Recommendation engine
- Push notifications for order updates
- Multi-currency and localization
- Loyalty points and rewards

For this **static frontend**, contributions are welcome for:

- Accessibility improvements (ARIA, keyboard nav)
- Performance (image compression, lazy loading)
- Additional UI pages (FAQ, blog, brand pages)
- Micro-interactions and animations

---

## 10. Credits and License

### Credits
- **Developer:** Jacob Kau
- **Built by:** Witty Highbrow Technologies
- **Contact:** [wittyhighbrowtechnologies@gmail.com](mailto:wittyhighbrowtechnologies@gmail.com)

### License
This project is **for educational and demonstration purposes only**. It is not intended for commercial use. All rights reserved by Witty Highbrow Technologies.

For commercial licensing of the full-stack WittyMart platform, contact the email above.
