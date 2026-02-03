# Scroll-Trigger-Sticky-Cards 🎨

## Demo 🎬
A premium interactive showcase featuring sticky cards with smooth scroll-triggered animations. Experience elegant card transitions and marquee text animations as you scroll through the Capsules® resort experience.

## Advanced Scroll Animations with Sticky Cards

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![GSAP](https://img.shields.io/badge/GSAP-88CE02?style=flat-square&logo=greensock&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)

A stunning interactive website featuring smooth scroll-triggered animations, sticky card effects, and dynamic marquee text loops. This project demonstrates advanced animation techniques using GSAP and Lenis to create a professional, premium user experience.

- **[Live Demo](https://your-live-url.netlify.app/)** - View the project in action
- **[GitHub Repository](https://github.com/Saurabh-git-hub/Scroll-Trigger-Sticky-Cards)** - View source code

---

## ✨ Features

- **Scroll-Triggered Animations** - Cards animate in with smooth scroll interactions
- **Sticky Card Effects** - Cards stick to viewport during scroll for dramatic effect
- **Marquee Text Loops** - Infinite horizontal scrolling text with GSAP animations
- **Smooth Scrolling** - Premium smooth scroll experience using Lenis
- **Text Split Animations** - Character-by-character reveal animations
- **ScrollTrigger Integration** - Advanced scroll timeline animations
- **Professional Design** - Modern dark theme with elegant typography
- **GSAP Animations** - Smooth, GPU-accelerated animations using GreenSock
- **Responsive Layout** - Fully optimized for all screen sizes
- **Dynamic Image Reveals** - Images animate with clip-path and scale effects
- **Hover Interactions** - Smooth transitions on card hover states
- **Custom Fonts** - Beautiful typography with responsive sizing

---

## 🛠️ Technologies Used

| Technology | Version | Purpose |
|-----------|---------|---------|
| **HTML5** | - | Semantic markup structure |
| **CSS3** | - | Advanced styling and animations |
| **JavaScript (ES6+)** | - | Dynamic functionality and event handling |
| **GSAP** | 3.14.2 | Professional-grade animation library |
| **GSAP ScrollTrigger** | - | Scroll-based animation plugin |
| **GSAP SplitText** | - | Text animation plugin |
| **Lenis** | 1.3.3 | Premium smooth scrolling library |
| **Vite** | 5.0.0+ | Fast build tool and dev server |

---

## 📦 Installation

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn package manager
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Quick Start

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Saurabh-git-hub/Scroll-Trigger-Sticky-Cards.git
   cd Scroll-Trigger-Sticky-Cards
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Start Development Server**
   ```bash
   npm run dev
   ```
   The application will open at `http://localhost:5173/`

4. **Build for Production**
   ```bash
   npm run build
   ```
   Optimized files will be in the `dist/` folder

---

## 💡 Usage

1. Navigate to the project directory
2. Run `npm install` to install dependencies
3. Run `npm run dev` to start the dev server
4. Open your browser to `http://localhost:5173/`
5. Scroll through the page to experience the animations
6. Observe smooth card animations and marquee text effects

### How to Customize

#### Modify Card Content

Edit `index.html` and update the card sections:
```html
<div class="card">
  <div class="card-marquee">
    <div class="marquee">
      <h1>Your Text Here</h1>
      <h1>Your Text Here</h1>
    </div>
  </div>
  <div class="card-wrapper">
    <div class="card-content">
      <div class="card-title">
        <h1>Your Card Title</h1>
      </div>
      <div class="card-description">
        <p>Your card description goes here...</p>
      </div>
    </div>
  </div>
</div>
```

#### Adjust Animation Timing

In `script.js`, modify GSAP timeline durations:
```javascript
gsap.to(element, {
  duration: 0.5,  // Change this value
  ease: "power2.out",
});
```

#### Customize Scroll Speed

In `script.js`, adjust Lenis scroll speed:
```javascript
const lenis = new Lenis({
  wheelMultiplier: 1, // Increase for faster scroll
  smoothWheel: true,
});
```

#### Change Colors and Styling

Modify `styles.css` to customize:
- Background colors and gradients
- Font sizes and typography
- Spacing and layout
- Card border radius and effects
- Animation easing functions

---

## 📁 Project Structure

```
Scroll-Trigger-Sticky-Cards/
├── index.html                  # Main HTML file with card structure
├── script.js                   # Main animation logic with GSAP
├── marquee.js                  # Marquee animation module
├── styles.css                  # All styling and animations
├── vite.config.js              # Vite configuration
├── package.json                # Project dependencies
├── package-lock.json           # Dependency lock file
├── public/                     # Static assets
│   ├── card-img-1.png         # Card images
│   ├── card-img-2.png
│   ├── card-img-3.png
│   └── card-img-4.png
├── dist/                       # Production build (generated)
├── node_modules/               # Dependencies (generated)
├── README.md                   # Project documentation
└── .github/                    # GitHub configuration
```

---

## 🔧 How It Works

### Animation Flow

1. **Page Load** - GSAP and Lenis initialize on DOM ready
2. **Smooth Scroll** - Lenis takes over scroll handling
3. **Scroll Detection** - ScrollTrigger monitors scroll position
4. **Card Animation**:
   - Cards trigger animation at specific scroll points
   - Text splits into characters
   - Characters animate in with staggered timing
   - Cards stick to viewport during scroll
5. **Marquee Animation** - Infinite horizontal text loop plays continuously
6. **Description Reveal** - Card descriptions fade and slide in on scroll

### Key Components

**Marquee Animation Module** (`marquee.js`)
```javascript
export function setupMarqueeAnimation() {
  const marqueeItems = gsap.utils.toArray(".marquee h1");
  if (marqueeItems.length > 0) {
    const tl = horizontalLoop(marqueeItems, {
      repeat: -1,
      paddingRight: 30,
    });
  }
}
```

**Text Split Animation** (`script.js`)
```javascript
const split = new SplitText(title, {
  type: "chars",
  charsClass: "char",
  tag: "div",
});
```

**ScrollTrigger Setup**
```javascript
gsap.registerPlugin(ScrollTrigger);
// ScrollTrigger configuration for card animations
```

---

## 🎯 Customization Guide

### Modify Marquee Speed

In `marquee.js`, adjust the `pixelsPerSecond` value:
```javascript
let pixelsPerSecond = (config.speed || 1) * 100;
// Increase the multiplier (e.g., 1.5) for faster marquee
```

### Change Card Animation Easing

Replace easing functions in `script.js`:
- `"none"` - Linear
- `"power1.out"` - Light ease
- `"power2.out"` - Medium ease
- `"power3.out"` - Strong ease
- `"back.out"` - Bounce effect
- `"elastic.out"` - Spring effect

### Adjust Scroll Smoothing

Modify Lenis configuration in `script.js`:
```javascript
const lenis = new Lenis({
  duration: 1.2,           // Scroll duration
  easing: (t) => t,        // Easing function
  wheelMultiplier: 1,      // Scroll speed multiplier
  smoothWheel: true,       // Enable smooth wheel
});
```

### Update Colors

Edit CSS color scheme in `styles.css`:
```css
body {
  background-color: #0f0f0f;  /* Dark background */
  color: #fff;                /* Text color */
}

section {
  background-color: #0f0f0f;
}
```

### Change Typography

Update font imports and sizes:
```css
h1 {
  font-size: 5rem;
  font-weight: 500;
  letter-spacing: -0.1rem;
}
```

---

## 🌐 Browser Support

| Browser | Support | Version |
|---------|---------|---------|
| Chrome | ✅ Full | Latest |
| Firefox | ✅ Full | Latest |
| Safari | ✅ Full | Latest |
| Edge | ✅ Full | Latest |
| Mobile Chrome | ✅ Full | Latest |
| Mobile Safari | ✅ Full | Latest |

---

## ⚡ Performance Optimization

- **GPU-Accelerated Animations** - GSAP uses transform & opacity for smooth 60fps performance
- **Lazy Loading** - Images load on demand
- **Efficient Event Handling** - Scroll events throttled with GSAP ticker
- **Optimized Build** - Vite provides fast bundling and code splitting
- **Tree Shaking** - Unused code automatically removed in production
- **Asset Optimization** - Images optimized in public folder
- **CSS Minification** - Production build minimizes CSS
- **JS Minification** - Production build minifies JavaScript

---

## 📝 Available Scripts

```bash
# Start development server with hot reload
npm run dev

# Build for production (creates dist/ folder)
npm run build

# Preview production build locally
npm run preview
```

---

## 🎓 Learning Resources

- **[GSAP Documentation](https://greensock.com/docs/)** - Animation library docs
- **[GSAP ScrollTrigger Docs](https://greensock.com/scrolltrigger/)** - Scroll animations
- **[GSAP SplitText Docs](https://greensock.com/splittext/)** - Text animations
- **[Lenis Documentation](https://lenis.darkroom.engineering/)** - Smooth scroll library
- **[Vite Documentation](https://vitejs.dev/)** - Build tool docs
- **[MDN Web Docs](https://developer.mozilla.org/)** - Web API references
- **[CSS Tricks](https://css-tricks.com/)** - CSS tutorials and tips
- **[JavaScript Info](https://javascript.info/)** - JavaScript fundamentals

---

## 🐛 Troubleshooting

### Dependencies Not Installing
- Delete `node_modules` and `package-lock.json`
- Run `npm cache clean --force`
- Run `npm install` again

### Animations Not Working
- Check browser console (F12) for errors
- Verify GSAP is loaded correctly
- Ensure ScrollTrigger plugin is registered
- Check that HTML structure matches expected format

### Scroll Not Smooth
- Verify Lenis is properly initialized
- Check for JavaScript errors in console
- Ensure `lenis.raf()` is called in GSAP ticker
- Try resetting scroll position

### Images Not Displaying
- Check image paths in `public/` folder
- Verify file names match HTML references
- Clear browser cache and reload
- Check browser dev tools Network tab

### Build Errors
- Ensure Node.js version is v14 or higher
- Delete `dist/` folder and rebuild
- Check for syntax errors in JavaScript files
- Verify all imports are correct

---

## 📄 License

This project is open source and available under the **MIT License**. Feel free to use, modify, and distribute this project for personal and commercial purposes.

```
MIT License

Copyright (c) 2024 Saurabh Chauhan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 👨‍💻 Author

**Saurabh Chauhan**

<div align="center">

### Connect With Me

[![Portfolio](https://img.shields.io/badge/Portfolio-000?style=for-the-badge&logo=vercel&logoColor=white)](https://saurabh-s-w-e.vercel.app/)
[![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Saurabh-git-hub)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/saurabhchauhan2000/)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://x.com/saurabh_10_12)

</div>

---

##  Acknowledgments

- **[GSAP (GreenSock)](https://greensock.com/)** - Professional animation library
- **[Lenis](https://lenis.darkroom.engineering/)** - Premium smooth scrolling
- **[Vite](https://vitejs.dev/)** - Fast build tool and dev server
- **[Google Fonts](https://fonts.google.com/)** - Beautiful typography
- **[GitHub](https://github.com/)** - Version control and hosting

---

<div align="center">

### Support This Project

⭐ **If you found this helpful, please give it a star!**

🍴 **Feel free to fork and contribute**

💬 **Share your feedback and suggestions**

---

**Made with ❤️ by Saurabh Chauhan**

*Keep coding, keep creating, keep learning!* 🚀

</div>
