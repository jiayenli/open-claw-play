# Open Claw Play

A fun collection of web projects built with Vue 3 and Tailwind CSS.

## Projects

### 🎲 Random Joke Generator
A fun and interactive joke generator built with a complete Vue 3 + Vite architecture.

**Features:**
- 🎉 Random joke generator with 20 pre-loaded jokes
- 📋 Copy to clipboard functionality
- 📤 Share jokes via native share API
- 📊 Joke counter tracking
- 🎨 Beautiful gradient UI with Tailwind CSS
- 📱 Fully responsive design
- ⚡ Fast development with Vite's HMR
- 🏗️ Professional Vue 3 project structure

**Tech Stack:**
- Vue 3 (Composition API with `<script setup>`)
- Vite (modern build tool)
- Tailwind CSS (with PostCSS)
- Node.js & npm

**Project Structure:**
```
open-claw-play/
├── src/
│   ├── components/
│   │   └── JokeGenerator.vue
│   ├── App.vue
│   ├── main.js
│   └── style.css
├── index.html
├── vite.config.js
├── tailwind.config.js
├── postcss.config.js
└── package.json
```

## Getting Started

### Development
```bash
npm install
npm run dev
```
The app will be available at `http://localhost:5173` (or the next available port)

### Build
```bash
npm run build
```
Creates optimized production build in `dist/` directory

### Preview
```bash
npm run preview
```
Preview the production build locally

## Public URL (Codespaces)
Access the development server via your Codespaces forwarded URL when running `npm run dev`

## Future Ideas
- Integration with external joke APIs
- Multiple joke categories
- User favorites system
- Dark mode
- Multi-language support

## License
MIT
