# New site theme — install guide

## What's in here
- `preview.html` — a standalone, clickable mockup of the whole redesign (Home / Blog / Projects / About). Open it in a browser to see it in action, tab through the nav.
- `_layouts/default.html` — replaces your current theme's layout (header, nav, footer).
- `assets/css/style.css` — the new stylesheet. All colors/fonts/spacing live here as CSS variables at the top.
- `index.md`, `about.md`, `blog.md`, `projects.md` — your four pages, rebuilt with your real content.

## How to install into your existing repo (lcomet/linamolinascomet)

1. **Remove the old theme.** In `_config.yml`, delete or comment out the line that pulls in the Indigo theme, e.g.:
   ```yaml
   # remote_theme: sergiokopplin/indigo
   ```
   Also remove any `theme:` line if present.

2. **Copy in the new files**, keeping the same folder structure:
   - `_layouts/default.html` → your repo's `_layouts/default.html`
   - `assets/css/style.css` → your repo's `assets/css/style.css`
   - `index.md`, `about.md`, `blog.md`, `projects.md` → repo root (overwrite the existing ones)

3. **Keep your existing `_posts/` folder as-is.** The blog page automatically lists everything in `site.posts`.

4. **Projects page:** your old theme listed "my project" as a post too. To make it show up under **Projects** specifically, add this to that post's front matter:
   ```yaml
   categories: [projects]
   ```
   If you'd rather list projects manually instead of by category, replace the loop in `projects.md` with a plain list of `entry-card` links (copy the pattern already used in the fallback block there).

5. **Profile photo:** already wired to `/assets/images/profile.jpg`, same path as before — no change needed if that file is still there.

6. Commit and push — GitHub Pages will rebuild automatically.

## Customizing
- Colors, fonts, radius: all at the top of `assets/css/style.css` under `:root`.
- The node-graph illustration on the homepage is inline SVG inside `index.md` — edit the `<circle>`/`<text>` labels to change what it connects to.
- Everything is plain CSS (no build step, no framework) — safe to hand-edit.
