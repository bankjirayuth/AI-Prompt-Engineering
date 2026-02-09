# Internal Presentation - AI Prompt Engineering

This file documents the structure, styling, and functionality of the "Internal Presentation" project for reference by future AI assistants and developers.

## 1. Project Overview
This project is a **Web-Based Presentation Deck** (HTML/CSS/JS) designed to teach "AI Prompt Engineering" in a visually rich, interactive format.

- **Stack**: Pure HTML5, TailwindCSS (CDN), Vanilla JavaScript.
- **Assets**: FontAwesome (Icons), Google Fonts (Inter, Kanit, JetBrains Mono, Sarabun).
- **Hosting**: Configured for Vercel Static Deployment.

## 2. File Structure & Architecture

### **Core Engine**
- **`presentation.html`**: The main "Player" or container application.
    - Loads individual slides via `<iframe id="slideFrame">`.
    - Handles global navigation (Prev/Next buttons, keyboard shortcuts).
    - Manages responsive scaling (`transform: scale()`) to fit 1280x720 slides on any screen.

### **Slides (Content)**
- **`[1-14].html`**: Individual slide files.
    - Each slide is a standalone HTML file.
    - Designed for 1280x720 resolution (16:9).
    - Contains its own scoped styles and scripts (e.g., interactive quizzes).

### **Configuration**
- **`vercel.json`**: Vercel deployment configuration.
    - **Rewrites**: Maps root `/` to `/presentation.html`.
    - **Clean URLs**: Maps `/1` → `/1.html`, etc.

## 3. Design System & Styling

Global styles are embedded in each HTML file but follow a consistent theme:

- **Theme**: Dark Mode (Background: Slate 900 `#0f172a`).
- **Typography**:
    - **English Headings/UI**: `Inter`
    - **Thai Text**: `Kanit` (Essential for localization)
    - **Code/Technical Terms**: `JetBrains Mono`
    - **Badges/Labels**: `Sarabun`
- **Visual Effects**:
    - **Glassmorphism**: `.glass-panel` (Backdrop blur, semi-transparent borders).
    - **Neon Glows**: `.glow-blob-purple`, `.glow-blob-cyan` (Background ambient lights).
    - **Gradients**: Grid backgrounds (`.grid-bg`).

## 4. Key Interactive Components

### **Quiz Module (e.g., in `3.html`)**
- Interactive quick-check quizzes embedded directly in slides.
- **Features**:
    - Single-choice selection logic.
    - Immediate feedback (Green/Red colors, ✅/❌ icons).
    - Explanation toggle (Show valid reasoning on click).
    - Reset logic when toggling visibility.

### **Navigation System (in `presentation.html`)**
- Prev/Next buttons with hover states.
- Progress bar indicator at the top.
- Keyboard support (Arrow keys).

## 5. Development Guidelines for AI

When modifying this project:
1.  **Preserve the Theme**: Always use the existing Tailwind classes and custom CSS variables (glass panels, glows).
2.  **Maintain Font Consistency**: Use `thai-font` class for Thai text and `code-font` for technical terms.
3.  **Standalone Slides**: Remember that edits to one slide (`3.html`) do not affect others (`4.html`) unless you edit common assets or templates.
4.  **Deployment**: The project is static. No build step required. Deploying to Vercel requires `vercel.json` for proper routing.
