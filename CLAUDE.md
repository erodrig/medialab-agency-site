# MediaLab Agency Website

Static marketing site built with Astro + Tailwind CSS, deployed to AWS S3 + CloudFront.

## Commands

- `npm run dev` — local dev server at localhost:4321
- `npm run build` — build to `dist/`
- `npm run preview` — preview production build locally

## Site Structure

All content is in Spanish. Each section is a separate `.astro` component:

| Section | File | Description |
|---------|------|-------------|
| Navigation | `src/components/Navbar.astro` | Fixed top nav with logo, contact link, social icons |
| Hero | `src/components/Hero.astro` | Full-screen hero with headline and CTA |
| Stats | `src/components/Stats.astro` | Animated counters (employees, creators, projects) |
| Clients | `src/components/Clients.astro` | Client logo grid — add logos to `public/images/clients/` |
| Partnerships | `src/components/Partnerships.astro` | Partner logo grid |
| Work Gallery | `src/components/WorkGallery.astro` | Portfolio items linking to Instagram |
| Locations | `src/components/Locations.astro` | 7 LATAM office cities |
| CTA | `src/components/CTA.astro` | Call-to-action banner |
| Contact | `src/components/ContactForm.astro` | Form that POSTs to API Gateway |
| Footer | `src/components/Footer.astro` | Logo, links, copyright |

The page composition is in `src/pages/index.astro`.

## Conventions

- All user-facing text is in **Spanish**
- Styles use **Tailwind utility classes** inline — no separate CSS files per component
- Brand colors defined in `tailwind.config.mjs`: black (#0a0a0a), dark (#1a1a1a), accent (#e63946)
- Images go in `public/images/` subdirectories
- Contact form API URL is set via `PUBLIC_CONTACT_API_URL` env var

## Deployment

Push to `main` triggers GitHub Actions → builds → syncs to S3 → invalidates CloudFront.
Currently serving at `https://www1.medialab.agency`.
