# RTL header menu for hosted site builders

A drop-in, right-to-left site header for hosted site builders, built from a short config block.

- Logo (or text) on its own row, the menu on a second row.
- Dropdowns that open on hover (desktop) and on tap or keyboard (touch, accessibility).
  Clicking outside or pressing Escape closes them.
- A burger menu below 768px. It works with CSS alone, no script needed for the toggle.
- The current page is highlighted, and so is its dropdown.
- A call-to-action button at the end, optional.
- Menu labels are inserted as text, never as HTML.

## Install

1. In your site builder, turn off the theme's own header.
2. In the footer or custom code area (runs on every page), paste [`header-menu.html`](header-menu.html).
3. Edit the `CONFIG` block:

```js
var CONFIG = {
  brand: { text: 'My Company', logo: '', href: '/' },
  menu: [
    { label: 'Home', href: '/' },
    { label: 'Services', items: [
      { label: 'First', href: '/service-1' },
      { label: 'Second', href: '/service-2' }
    ]},
    { label: 'Blog', href: '/blogs' }
  ],
  cta: { label: 'Contact', href: '/contact', newTab: false }
};
```

Colors are CSS variables at the top of the style block (`--ink`, `--accent`, `--cta`, …).

The script waits for the page body, so it also works when the builder places the snippet in the
page head.
