# RTL blog fix for hosted site builders

Repairs Hebrew (and other right-to-left) blog posts on hosted site builders without editing them.

## The problem

- **Lost emoji.** Emoji outside the Basic Multilingual Plane (most of them, e.g. 🔒 📌 🚨) can
  come out as a plain `?` after saving a post, so lines start with "? ...".
- **Wrong direction.** Blocks without an explicit direction are laid out left-to-right, so a
  leading symbol jumps to the wrong side of a Hebrew line.

## What the script does

On blog pages only (`/blog` or `/blogs`, set by `BLOG_PATH`):

1. A `?` left at the start of a line, where an emoji used to be, becomes ✔️. In headings it is
   simply removed.
2. Every text block gets `dir="rtl"`, so symbols stay at the start of the line.
3. Content loaded later, like infinite scroll or the next post, is fixed as it appears.

The posts themselves are not changed. The fix happens in the visitor's browser.

## Install

1. Open your site builder's footer or custom code area (the part that runs on every page).
2. Paste the contents of [`blog-fix.html`](blog-fix.html) and publish.

Settings at the top of the script:

| Setting | Default | Meaning |
|---|---|---|
| `BLOG_PATH` | `/blog`, `/blogs` | Which pages are the blog |
| `REPLACEMENT` | `✔️ ` | What a lost emoji becomes |
| `SKIP` | `header, nav, pre, code, …` | Areas that are never touched |

## Tip for new posts

Use symbols from the Basic Multilingual Plane, which survive saving: ✔️ ✅ ⚠️ ⚡ ★ ☎️ ✉️ ⛔ ➜.
