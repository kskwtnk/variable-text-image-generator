# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a React-based image generator that creates customizable 1920x1080 images with text overlays. Users can select templates, input text through forms, and download generated PNG images. The application uses Satori to convert React components to SVG/PNG for image generation.

## Development Commands

- `pnpm dev` - Start development server
- `pnpm build` - Build for production (TypeScript compilation + Vite build)
- `pnpm preview` - Preview production build locally
- `pnpm lint` - Run ESLint and Prettier checks
- `pnpm lint:fix` - Auto-fix ESLint issues and format with Prettier

## Architecture

### Core Architecture

The application follows a template-based architecture where each image template is a React component that receives text props and renders styled content over background images.

### Key Components

- **Templates** (`src/templates/`): React components that define image layouts and styling
- **Pages** (`src/pages/`): Root page with form inputs and Render page for image generation
- **Routes** (`src/routes.ts`): Configuration mapping paths to templates with default values
- **Utils** (`src/utils/`): Image processing utilities for SVG to PNG conversion

### Template System

Each template in `src/templates/` is a React component that:
- Accepts text props for customization
- Uses absolute positioning with `1920x1080` dimensions
- Loads background images from `/public/` directory
- Applies custom fonts and styling

To add a new template:
1. Create component in `src/templates/`
2. Add background image to `/public/`
3. Register in `src/routes.ts` with path and default values

### Image Generation Flow

1. User fills form on root page → navigates to `/render/{template}`
2. Render page loads template component with user's text
3. Satori converts React component to SVG
4. SVG is converted to PNG blob for download

## Technical Stack

- **React 18** with TypeScript
- **Vite** for build tooling and dev server
- **Satori** for React-to-image conversion
- **React Router DOM** for navigation
- **pnpm** as package manager
- **GitHub Pages** deployment via GitHub Actions

## Development Notes

- Uses SWC compiler for fast TypeScript compilation
- Configured for GitHub Pages deployment with base path from package.json name
- Background images must be placed in `/public/` and referenced with absolute paths
- Templates should maintain 1920x1080 aspect ratio for consistent output
- Fonts are loaded from `/public/fonts/` directory
