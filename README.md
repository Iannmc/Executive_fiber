# Executive Fiber Website

Static website for Executive Fiber (Matuu, Machakos County, Kenya). Plain HTML, CSS and JavaScript with no build step, hosted on Netlify at https://executivefiber.com.

## File structure

```
/ (site root)
├── index.html        Home
├── about.html        About us
├── services.html     ISP services
├── packages.html     Internet packages and pricing
├── digital.html      Digital services
├── contact.html      Contact and connection request form (Netlify Forms)
├── privacy.html      Privacy policy
├── 404.html          Not-found page (Netlify serves it automatically)
├── ef-shared.css     Shared styles for all pages (colours, nav, footer, buttons)
├── ef-shared.js      Shared scripts (mobile menu, etc.)
├── robots.txt        Allows all crawlers
└── images/
    ├── logo-mark.svg           Logo mark (signal arcs) used in nav and footer
    ├── favicon-16x16.png
    ├── favicon-32x32.png
    ├── apple-touch-icon.png
    ├── icon-192.png
    └── icon-512.png
```

## Design

- Fonts: Fraunces (headings), Plus Jakarta Sans (body), JetBrains Mono (numbers/code), loaded from Google Fonts.
- Colours: navy `#080F1E` background, cyan `#00CFE8` accent. Change these in the `:root` variables at the top of `ef-shared.css`.

## The logo

The logo is the file `images/logo-mark.svg`, shown beside the "ExecutiveFiber" text in the nav and footer of every page. The markup is:

```html
<a href="index.html" class="logo">
  <img src="images/logo-mark.svg" alt="" class="logo-img" width="38" height="28">
  <span class="logo-text">Executive<em>Fiber</em></span>
</a>
```

- Size and spacing are controlled by `.logo` and `.logo-img` in `ef-shared.css`.
- `404.html` uses absolute paths (`/images/logo-mark.svg`, `href="/"`) so it works from any URL.
- To change the logo, replace `images/logo-mark.svg` (keep the same filename). No HTML edits are needed.

## Deploying to Netlify

1. Copy changed files into the site folder, keeping the structure above.
2. Drag the folder onto Netlify (Deploys tab) or push to the connected repository.
3. Hard-refresh the browser (Ctrl+Shift+R) so cached CSS is replaced.

## Editing tips

- Nav and footer are repeated in each HTML file. A change to them (links, logo) must be made in all 8 pages.
- Styles shared by every page go in `ef-shared.css`. Page-specific styles are in a `<style>` block in that page.
- The contact form uses Netlify Forms. Submissions appear in Netlify under Forms, so the form's `name` attribute and hidden `form-name` field must not be removed.

## Related

The Executive Fiber customer mobile app (Flutter + Supabase) is a separate project and is not part of this folder.
