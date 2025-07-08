# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is Ryan Renna's personal portfolio website - a static site showcasing iOS development skills and projects. The site is hosted on GitHub Pages at www.ryanrenna.com.

## Tech Stack

- **Frontend**: Vanilla HTML, CSS, JavaScript (no frameworks or build tools)
- **External Libraries**: 
  - Swiper.js (testimonial carousel)
  - EmailJS (contact form)
  - SweetAlert (notifications)
  - Unicons (icon library)
- **Hosting**: GitHub Pages with custom domain

## Commands

Since this is a static site with no build process:

- **Run locally**: Open `index.html` in a web browser or use a local server:
  ```bash
  # Python 3
  python -m http.server 8000
  
  # Python 2
  python -m SimpleHTTPServer 8000
  
  # Node.js (if http-server is installed globally)
  http-server
  ```

- **Deploy**: Push changes to GitHub main branch (auto-deploys via GitHub Pages)

## Architecture

### File Structure
- `index.html` - Single page application entry point
- `assets/css/styles.css` - All styles including theme variables
- `assets/js/main.js` - All JavaScript functionality
- `assets/img/` - Images for portfolio, skills icons, etc.
- `assets/pdf/Resume.pdf` - Current resume
- `assets/snaps/` - Social media preview images

### Key Features
1. **Theme System**: Dark/light mode toggle using CSS variables and localStorage
2. **Section Navigation**: Smooth scroll with active section highlighting
3. **Contact Form**: EmailJS integration (public key in main.js:1056)
4. **Project Modals**: Dynamic modal system for project details
5. **Responsive Design**: Mobile-first with breakpoints at 350px, 568px, 768px, 1024px

### CSS Architecture
- Uses HSL color system with configurable hue variable (currently 340)
- CSS custom properties for theming
- BEM-like naming convention
- Organized by sections with clear comments

### JavaScript Patterns
- Event delegation for dynamic content
- LocalStorage for theme persistence
- Form validation before EmailJS submission
- Intersection Observer could be added for scroll animations

## Development Guidelines

When modifying this codebase:

1. **Adding Projects**: Update the projects section in index.html following the existing modal pattern
2. **Updating Resume**: Replace `assets/pdf/Resume.pdf` and update the download link
3. **Changing Theme Colors**: Modify `--hue-color` in styles.css:42
4. **Adding Skills**: Follow the accordion pattern in the skills section
5. **Social Links**: Update footer social links or contact section links

## Important Notes

- No linting or build process exists - manually ensure code quality
- Test responsive design at key breakpoints
- Check dark/light theme when making CSS changes
- EmailJS service ID and template ID are in main.js:1057-1058
- Google Analytics ID is in index.html:19