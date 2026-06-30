# Confederation College Astro Starter

A starter template for Confederation College web projects built with Astro.js, featuring the college's brand styling.

## 🚀 Getting Started

To create a new project using this Confederation College Astro theme:

### Create a new project using this template

```bash
npm create astro@latest my-project -- --template ConfederationCollege-ca/cc-astro-starter
```

```bash
# Navigate to project folder
cd my-project

# Install dependencies
npm install

# Start development server
npm run dev
```

## 🎓 Features

- Confederation College brand colors
- Tailwind CSS for styling
- Typography with Outfit font
- Responsive design
- Fast performance with Astro.js

## 🚀 Project Structure

```text
/
├── public/
│   ├── favicon.svg           # Confederation College favicon
│   └── site.webmanifest      # Web app manifest file
├── src/
│   ├── components/           # Reusable UI components
│   │   ├── Footer.astro      # Site footer
│   │   ├── TypographyTest.astro  # Typography showcase
│   │   └── svg/              # SVG components as Astro files
│   │       ├── LogoHorizontal.astro     # CC horizontal logo
│   │       ├── LogoVertical.astro       # CC vertical logo
│   │       └── LogoIcon.astro           # CC logo icon/mark
│   ├── layouts/              # Page layouts
│   │   └── Layout.astro      # Main layout with CC branding
│   ├── pages/                # Route pages
│   │   ├── index.astro       # Homepage
│   │   └── 404.astro         # Error page
│   ├── styles/               # Global styles
│   │   └── global.css        # Tailwind + CC brand colors via @theme
│   └── env.d.ts              # Ambient type declarations
├── .github/workflows/ci.yml  # CI: format check, type check, build
├── .editorconfig             # Cross-editor whitespace/charset rules
├── .nvmrc                    # Pinned Node version
├── .prettierrc.json          # Prettier + Astro/Tailwind plugins
├── astro.config.mjs          # Astro config (Tailwind v4 Vite plugin)
├── tsconfig.json             # TypeScript configuration (strict)
└── package.json              # Dependencies and scripts
```

## 🧞 Commands

| Command                | Action                                                   |
| :--------------------- | :------------------------------------------------------- |
| `npm install`          | Installs dependencies                                    |
| `npm run dev`          | Starts local dev server at `localhost:4321`              |
| `npm run build`        | Type-check, then build your production site to `./dist/` |
| `npm run preview`      | Preview your build locally, before deploying             |
| `npm run check`        | Type-check `.astro`/`.ts` files with `astro check`       |
| `npm run format`       | Format the codebase with Prettier                        |
| `npm run format:check` | Verify formatting without writing (used in CI)           |
| `npm run astro ...`    | Run CLI commands like `astro add`, `astro check`         |

## 🔧 Customization

This starter includes Confederation College's brand colors and typography. You can customize the theme further by editing the Tailwind v4 `@theme` tokens in `src/styles/global.css` (Tailwind is configured CSS-first — there is no `tailwind.config.js`).

## 📐 Conventions

A few lightweight conventions keep the project consistent and type-safe without locking you into any particular architecture:

- **Component props are typed.** Each component declares a local `interface Props` in its frontmatter — Astro types `Astro.props` from it automatically (no import or cast). Components that wrap an element extend the matching attribute type (e.g. `astroHTML.JSX.SVGAttributes`, or `HTMLAttributes<"a">` from `astro/types`) so they inherit `class`, `aria-*`, etc.
- **Colors use theme tokens.** Brand colors live as `--color-*` tokens in `src/styles/global.css`. Reference them as Tailwind utilities (`text-accent`, `fill-accent-red`, …) or pass them into the SVG logo components as `var(--color-…)` rather than raw hex, e.g. `<LogoHorizontal primaryColor="var(--color-accent-red)" />`.
- **Types are enforced.** `npm run build` runs `astro check` first, so type errors fail the build. CI also runs `format:check`, `check`, and `build` on every push and pull request.
- **Formatting is automated.** Prettier (with the Astro and Tailwind class-sorting plugins) owns code style — run `npm run format` before committing.

### Intentionally not included

To stay a flexible starting point, this template deliberately ships **no** testing framework, CMS, component library, auth, or state management — those are decisions each project should make. Suggested additions when you need them: [Vitest](https://vitest.dev/) for tests, and Astro [Content Collections](https://docs.astro.build/en/guides/content-collections/) (with Zod schemas, already bundled) for type-safe content and data.

## 📝 License

This project is intended for Confederation College coursework and projects.
