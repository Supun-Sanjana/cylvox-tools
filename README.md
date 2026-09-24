# Cylvox Tools — CSS Gradients (v1)

Single-file, zero-dependency, drop-in ready. Matches your dark stone/violet identity
(swap the hex values in the :root block if your exact brand tokens differ).

## How to add this to your existing Next.js 15 site (no new domain needed)

**Option A — App Router page (recommended, gives it a proper /tools/gradients URL):**
1. Create `app/tools/gradients/page.tsx` in your Cylvox repo.
2. Either port the HTML into JSX (swap `class` → `className`, move the <style> into a
   CSS module or your Tailwind setup), or simplest for v1: render it as-is inside an
   iframe pointing at a static copy, or use `dangerouslySetInnerHTML` for the body content.
3. This gets you real Next.js routing, metadata, and it inherits your site's <head> —
   best for SEO since it's a first-party page on cylvox.com.

**Option B — static passthrough (fastest, ships today):**
1. Drop `gradients/index.html` into `public/tools/gradients/index.html`.
2. It becomes reachable at `cylvox.com/tools/gradients/index.html` with zero code changes.
3. Downside: it won't inherit your Next.js layout/nav, and the URL has a trailing
   `index.html` unless you configure a rewrite.

Given you already run Next.js, Option A is worth the ~20 minutes of porting for the
cleaner URL and shared nav — but Option B works today if you want it live immediately.

## What's in it
- 34 original gradients (not copied from any competitor's named list), tagged
  warm/cool/vivid/mono/pastel with a filter bar
- Click-to-copy CSS, clipboard API with a textarea fallback for older browsers
- No backend, no build step, no external JS dependencies (just Google Fonts)

## Growing this later
Same pattern as the image tools site: this is the seed of an "assets" section.
Natural next additions once this one is live and indexed:
- `/tools/shadows` — box-shadow generator/library
- `/tools/easing` — cubic-bezier curve visualizer
- `/tools/clip-path` — shape gallery

Each is copy-this-file-and-swap-the-data-array levels of effort once the pattern exists.

## Before going live
- Swap the placeholder hex values in `:root` for your actual Cylvox brand tokens if they differ
- Add this page to your sitemap.xml
- Link to it from your main nav or footer once it's live, so it gets internal link equity
