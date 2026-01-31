# Changelog

All notable changes to this project will be documented in this file.

## [2.0.0] - 2026-01-31

### Changed
- **Refactored to Full Vue 3 + Vite Architecture** ⚡
  - Migrated from CDN-based Vue to full build setup
  - Implemented proper component structure with `.vue` SFCs
  - Integrated Vite as build tool for faster development
  - Added Tailwind CSS with PostCSS processing
  - Separated concerns: App.vue, JokeGenerator.vue, main.js, style.css
  - Improved module organization and scalability

### Added
- Complete project setup with npm scripts (`npm run dev`, `npm run build`)
- Proper Vue 3 Composition API with `<script setup>`
- PostCSS and Tailwind CSS pipeline
- Development server configuration for Codespaces
- vite.config.js with Vue plugin support
- Source directory structure (/src)

### Technical Improvements
- Better module bundling and tree-shaking
- Faster hot module replacement (HMR) with Vite
- Professional project structure for scaling
- Proper CSS preprocessing with PostCSS

## [1.0.0] - 2026-01-31

### Added
- Initial release of Random Joke Generator
- Vue 3 (CDN) implementation for dynamic joke display
- Tailwind CSS for modern, responsive styling
- Gradient background and beautiful UI with rounded corners
- Get New Joke button with loading state
- Copy to Clipboard feature to save favorite jokes
- Share button with native share API support
- Joke counter to track how many jokes have been loaded
- 20 pre-loaded jokes with various themes
- Smooth animations and hover effects
- Mobile-responsive design
- Accessibility features with semantic HTML

### Features
- **Random Joke Display**: Click button to get a random joke
- **Copy Function**: Easily copy jokes to clipboard
- **Share Function**: Share jokes via native share API (mobile-friendly)
- **Joke Counter**: Track total jokes viewed
- **Loading Animation**: Visual feedback while loading jokes
- **Beautiful UI**: Gradient backgrounds, smooth transitions, and modern styling

### Technical Details
- Uses Vue 3 global build from CDN
- Uses Tailwind CSS CDN for styling
- No build process required - pure HTML/CDN approach
- Pure JavaScript - no external dependencies beyond Vue and Tailwind
- Single file HTML application for easy deployment

## Future Enhancements
- Integration with external joke API
- User favorites/bookmarking system
- Dark mode toggle
- Category filtering (programming, dad jokes, etc.)
- Multiple language support
