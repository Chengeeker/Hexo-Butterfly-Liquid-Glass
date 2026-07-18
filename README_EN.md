# Hexo-Butterfly-Glass

<p align="center">
<a href="./README.md">中文</a> | <a href="./README_EN.md">English</a>
</p>

<p align="center">
<strong>A modular Glass UI enhancement system designed for the Hexo Butterfly theme.</strong><br>
Introduces Apple-style Liquid Glass and Material You dark mode design languages to Butterfly without modifying the theme's source code.
</p>

---

## ✨ Project Introduction

**Hexo-Butterfly-Glass** is a visual enhancement project developed for the Hexo Butterfly theme. Through independent CSS modules, this project provides a non-intrusive UI upgrade to the Butterfly theme, bringing modern operating system design languages (such as Apple Liquid Glass, macOS translucency, iOS Control Center, visionOS spatial UI, and Android Material You) to the blog interface.

The core philosophy of this project is **"Enhance, don't replace."**

We do not modify the underlying source code of the Butterfly theme. Instead, we achieve visual upgrades through a CSS Override Layer. This non-intrusive design offers the following advantages:
- **High Compatibility**: Custom modifications will not be overwritten when the Butterfly theme updates.
- **Low Maintenance Cost**: Modular CSS makes troubleshooting and modification straightforward.
- **Easy Migration**: Supports quick reuse across different Hexo sites.
- **Flexible Control**: Enhancement effects can be enabled or disabled at any time.

---

## 🌟 Core Features

### 🪟 Glassmorphism System
Upgrades existing Butterfly components into a modern glassmorphic UI. Utilizing techniques such as `backdrop-filter`, semi-transparent surfaces, multi-layer shadows, border transparency, and specular highlights, it achieves a visual texture similar to macOS Toolbars, iOS Panels, and visionOS Windows.
- **Covered Components**: Homepage post cards, sidebar widgets, right-side utility buttons, Table of Contents (TOC), and top navigation bar.

### 🌈 Ambient Light Background System
Constructs a dynamic ambient background purely with CSS, abandoning traditional static background images. It employs multi-layer gradients and ambient light effects, combined with glass refraction and spatial layering, to create an immersive experience reminiscent of macOS Sonoma wallpapers and visionOS spatial visuals. It supports independent Light/Dark mode designs with zero additional image dependencies.

### 🌙 Material You Dark Mode
Avoids the harsh contrast and reading fatigue caused by traditional pure black (`#000000`) dark modes, while preventing pure black backgrounds from nullifying glass effects. It adopts a combination of "dark gray surface + ambient color + low-brightness glass layer," improving reading comfort while maintaining the texture and visual coherence of modern systems.

### 🍎 Floating Glass Navbar
Redesigns the top navigation bar with a floating layout and rounded glass aesthetics. Combining a frosted glass background with shadow layering, it seamlessly adapts to both light and dark modes, drawing design inspiration from macOS Toolbars and visionOS Floating Panels.

### 🏷️ Capsule Tag System
Optimizes default flat tags into a modern capsule style (Capsule UI), referencing the design specifications of iOS Tags, Material Chips, and macOS Labels to elevate the interface's refinement and modernity.

---

## 🏗️ Design Architecture

This project strictly adheres to the **non-intrusive design** principle. The architectural hierarchy is as follows:

```text
Butterfly Theme (Native Theme)
       ↓
CSS Override Layer (This Project's CSS)
       ↓
Liquid Glass System (Final Visual Presentation)
```

**Unmodified Elements**: Butterfly source files, JavaScript logic, and template structures.  
**Guaranteed Outcome**: Seamless theme upgrades and independent operation of extension modules.

---

## 📂 Project Structure and Module Description

```text
butterfly-glass/
└── css/
    ├── glass-variable.css   # Global design variables (radius, shadow, blur, colors, etc.)
    ├── glass-background.css # Page background system (Light/Dark mode backgrounds)
    ├── glass-ambient.css    # Ambient light system (soft reflections, color atmosphere, spatial layering)
    ├── glass.css            # Core glass components (cards, sidebar, utility buttons)
    ├── glass-navbar.css     # Top floating glass navigation
    ├── glass-post.css       # Post page enhancement (content surface, reading experience optimization)
    ├── glass-tag.css        # Capsule tag system
    ├── glass-toc.css        # Glassmorphic Table of Contents
    └── glass-config.css     # Final override layer (specificity correction, compatibility patches, specific adjustments)
```

**Core Module Analysis**:
- **`glass-variable.css`**: Global design variable system, centrally managing core parameters like `--lg-radius-xl` and `--lg-blur-heavy`.
- **`glass.css`**: Core visual implementation, extensively utilizing `backdrop-filter`, `rgba()`, and `box-shadow` to construct the glass texture.
- **`glass-config.css`**: Acts as the final override layer, responsible for CSS specificity correction and compatibility patches for Butterfly.

---

## 🚀 Installation Guide

### 1. Clone the Repository
```bash
git clone https://github.com/yourname/Hexo-Butterfly-Glass.git
```

### 2. Deploy Files
Copy the project folder into the `source/` directory of your Hexo root directory.  
The final path should be: `Your_Blog_Root/source/butterfly-glass`.

### 3. Import CSS
Modify `_config.butterfly.yml` in the Hexo root directory. Import the following CSS files sequentially under `inject` -> `head` (**Note the order: variable files must be imported first**):

```yaml
inject:
  head:
    # - <link rel="stylesheet" href="/xxx.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-variable.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-background.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-page.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-ambient.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-navbar.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-post.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-tag.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-toc.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-search.css">
    - <link rel="stylesheet" href="/butterfly-glass/css/glass-config.css">
  bottom:
    # - <script src="xxxx"></script>
    - <script src="/butterfly-glass/js/glass-config.js"></script>
```

### 4. Generate and Preview
```bash
hexo clean
hexo generate
hexo server
```

---

## 📱 Browser Compatibility

This project relies on modern CSS features. It is recommended to use the latest versions of the following browsers:
- Chrome / Edge
- Safari
- Firefox

**Core Dependency**: The browser must fully support the CSS `backdrop-filter` property.

---

## ❌ Discarded Design Choices (Design Trade-offs)

During development, several visual schemes were tested. However, to safeguard the core reading experience of the blog, they were deliberately restrained and removed:

| Discarded Choice | Reason for Removal |
| :--- | :--- |
| **Global Top Image Blending** | Unstable performance in dark mode and prone to interfering with main text readability. |
| **Right-side Floating Control Center** | Occupies main content space, leading to a noticeably degraded experience on mobile devices. |
| **Additional Hover Animations** | Butterfly's native interactions are already sufficient; extra animations offer limited visual return and can appear cluttered. |
| **Cover Image Blending Animations** | Disrupts the inherent reading rhythm and immersion of the blog. |

**Final Principle**: Maintain the blog-centric nature of Butterfly. Provide visual enhancement only, without interfering with content consumption.

---

## 🛣️ Roadmap

- [ ] Adapt to more native Butterfly pages
- [ ] Expand Material You dynamic color schemes
- [ ] Develop automated configuration and theme generation tools
- [ ] Port to other static site generators like Astro / Hugo
- [ ] Support more custom UI components

---

## 🤝 Contributing

Contributions via Issues or Pull Requests are welcome, including but not limited to:
- Adding new UI components or visual effects
- Fixing known bugs or style conflicts
- Optimizing browser compatibility
- Improving documentation and translations

---

## 📄 License

This project is open-source under the [MIT License](./LICENSE).

---

## ❤️ Acknowledgements

- [Hexo Butterfly Theme](https://github.com/jerryc127/hexo-theme-butterfly): For providing an excellent theme foundation.
- **Apple Design Language**: For design inspiration regarding Liquid Glass and spatial UI.
- **Material Design Community**: For references on Material You dark mode and dynamic color systems.

---

<p align="center">
<strong>Made with ❤️ for Hexo Butterfly users.</strong>
</p>
