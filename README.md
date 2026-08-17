# 180 Degrees Consulting | IIT Kharagpur Website

This repository contains the official website for **180 Degrees Consulting, IIT Kharagpur (180DC IIT KGP)**.

The site is built as a highly performant, responsive, single-page website served via Vite, using vanilla HTML5, custom CSS3 variables, and client-side JavaScript.

---

## 🌟 Key Features

- **3D Particle Globe**: An interactive, animated 3D particle globe in the hero banner powered by **Three.js** (loaded via CDN).
- **Interactive Portfolio Map**: A clickable, animated SVG World Map on the **Projects** tab highlighting past client locations and project cards.
- **Scroll Animations**: Smooth staggered reveal animations and page elements fading in as you scroll.
- **Dynamic Counters**: Stat counters (e.g., Lives Impacted, Projects Completed) that count up dynamically when scrolled into view.
- **Custom Cursor**: A modern, interactive green cursor element that dynamically expands on hoverable buttons and links.
- **Client & Partner Testimonials**: Carousel-style feedback cards showcasing partner recommendations.

---

## 📁 Project Structure

Since React and Tailwind CSS have been removed, the project is extremely lightweight and easy to maintain:

```bash
├── assets/                  # Directory containing all director and alumni photo assets
├── public/                  # Favicons and general vector icons
├── index.html               # The main website (contains HTML markup, custom CSS, and JS logic)
├── package.json             # Node scripts and development dependencies (Vite, Oxlint)
└── vite.config.js           # Simplified Vite configuration for serving the static files
```

---

## 🛠️ How to Run Locally

### Prerequisites
Make sure you have [Node.js](https://nodejs.org/) installed.

### 1. Install Dependencies
Run this command in the project root to install the development server:
```bash
npm install
```

### 2. Start the Development Server
Run the local dev server:
```bash
npm run dev
```
Open **`http://localhost:5173/`** in your browser. The page will automatically reload whenever you edit code in `index.html`.

### 3. Build for Production
To generate a production-ready folder (ready to host on GitHub Pages or a web server), run:
```bash
npm run build
```
This will output optimized files into the `/dist` directory.

---

## ✍️ Maintenance & Handover Guide (For Future Batches)

All styles, structures, and scripts are placed in **`index.html`** with explanatory comments.

### 🎨 1. Retheming Colours
To update the color scheme, locate the `:root` variables inside the `<style>` block (around line 29):
```css
:root {
  --g: #00843d;   /* Primary corporate green */
  --gl: #86bc2a;  /* Accent lime green */
  --k: #050807;   /* Main background (dark) */
  --w: #f3f4f6;   /* Off-white text */
}
```

### 🔢 2. Updating Stats Counters
To change the numbers in the stat grids, search for the `data-to` attribute in the HTML markup:
```html
<span class="ctr" data-to="1000000" data-fmt="1M+">1M+</span>
```
- `data-to`: The final number that the animation counts up to.
- `data-suf` / `data-fmt`: Any suffix added (like `%` or `+`).

### 👥 3. Updating Team Directors
To add or remove directors:
1. Search for `dir-grid` (around line 4130) inside the `#page-team` div.
2. Edit or duplicate a `<div class="dcard">` block.
3. Save their square headshot in `/assets` named as `firstname.jpg` (e.g., `assets/rachit.jpg`). The HTML image fallback will automatically display their initials if the image is missing.

### 🎓 4. Adding/Updating Alumni
To update where alumni work:
1. Search for `ac-grid` (around line 4229).
2. Edit or duplicate an `<div class="ac">` card block.
3. Place their photo in the `/assets` folder named exactly `First Last.jpg` (e.g., `assets/Moulik.jpg`) and link it in the `<img>` tag:
   ```html
   <div class="ac-av"><img src="assets/Firstname.jpg" alt="Name" onerror="this.remove()">F</div>
   ```

### 📂 5. Adding Projects
To add client engagements to the map list:
1. Search for `#page-projects` (around line 3078).
2. Copy any card block inside `<div class="proj-left">` or `<div class="proj-right">` and update the company name, tag, and description.
