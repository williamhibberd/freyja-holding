# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Freja is the website for FREYJA, a Nordic/Northumbrian restaurant opening Autumn 2026. Built with Astro 6, Tailwind CSS 4, and TypeScript (strict mode).

## Commands

- `npm run dev` — Start dev server at localhost:4321
- `npm run build` — Production build to `./dist/`
- `npm run preview` — Preview production build locally

## Architecture

- **Astro 6** static site with file-based routing (`src/pages/`)
- **Tailwind CSS 4** via Vite plugin (configured in `astro.config.mjs`), using the new `@theme` directive
- Custom design system defined in `src/styles/global.css` — all default Tailwind scales are reset (`--color-*: initial`, `--spacing-*: initial`, etc.) and replaced with project-specific values
- Two custom fonts: **Telegraf** (sans-serif, `font-telegraf`) and **Romie** (serif, `font-romie`); font files served from `public/fonts/`
- Body defaults to `font-romie`; Telegraf is used for UI elements like the ticker
- Images stored in `src/images/` (processed by Astro's image pipeline)
- Static assets in `public/` (served as-is)
- Requires Node >= 22.12.0

## Tailwind Conventions

- Spacing unit is `0.0625rem` (1px) — use raw numbers as pixel values (e.g., `h-42` = 42px)
- Custom variant `touch` targets `pointer: coarse` devices
- Default transition: 600ms with `cubic-bezier(0.4, 0, 0.2, 1)`
