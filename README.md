# Anio Legacy Logo - ASCII Hover Animation

A creative, interactive ASCII logo animation project utilizing HTML5 Canvas and Vanilla JavaScript. As you hover over the ASCII art, the characters repel from the mouse cursor, creating a dynamic, physics-based fluid interaction.

<img width="1920" height="1080" alt="Screenshot (447)" src="https://github.com/user-attachments/assets/9dc7d266-13b0-41a5-bdc3-d8e0b7cc2020" />

## ✨ Features

- **Interactive Physics**: The ASCII grid reacts to cursor movements with simulated spring physics and damping.
- **Dynamic ASCII Mapping**: Samples a source logo image and maps its pixels to ASCII characters based on brightness thresholds.
- **Responsive Layout**: Adjusts cell sizes and recalculates the grid upon window resizing for optimal viewing on both desktop and mobile.
- **Vite Integration**: A fast and modern frontend build tool for instant HMR and optimized production bundling.

## 🛠️ Tech Stack

- **HTML5 Canvas** - For rendering the ASCII grid and character animations.
- **Vanilla JavaScript** - Core logic for sampling image brightness and applying physics (spring/damping formulas).
- **Vite** - For serving and building the project.
- **CSS3** - Layout and basic styling.

## 📁 Project Structure

```text
.
├── index.html       # Entry point containing the canvas and source logo
├── script.js        # Core logic for ASCII conversion and physics animation
├── styles.css       # Basic resets and full-screen canvas layout
├── package.json     # Vite dependencies and scripts
├── .gitignore       # Git ignore rules
└── public/
    └── logo.png     # The source image used for the ASCII effect
```

## 🚀 Setup & Installation

Ensure you have [Node.js](https://nodejs.org/) installed.

1. **Clone or Download the Repository**
2. **Navigate to the Project Directory**
   ```bash
   cd "ANIO Legacy Logo"
   ```
3. **Install Dependencies**
   ```bash
   npm install
   ```

## 💻 Usage

### Development Server
Start the local development server with Hot Module Replacement (HMR):
```bash
npm run dev
```
Open the provided URL (typically `http://localhost:5173/`) in your browser.

### Production Build
Create a minified and optimized build:
```bash
npm run build
```
The output will be placed in the `dist/` folder.

### Preview Production Build
Test the production build locally:
```bash
npm run preview
```

## 🧠 How it Works

1. **Image Sampling**: The hidden source logo is drawn to an offscreen canvas. The script iterates over the pixels, checking brightness levels.
2. **ASCII Grid**: If a pixel surpasses the brightness threshold, it's mapped to a character from the `ASCII_CHARS` string.
3. **Physics Engine**: Each character acts as a particle with `offsetX`, `offsetY`, `velX`, and `velY`. When the mouse moves near a particle, a repulsive force is applied.
4. **Spring & Damping**: To return characters to their original positions, a spring force pulls them back to `(0, 0)` offsets, while damping gradually slows their velocity, preventing infinite oscillation.
