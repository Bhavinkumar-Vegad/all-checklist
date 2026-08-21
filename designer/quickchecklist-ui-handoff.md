## States (the ones engineering will invent if you do not):

* [ ] Empty, 1 item, 12 items, 100+ (pagination/overflow).
* [ ] Loading (skeleton vs spinner vs stale-while-revalidate).
* [ ] Error: inline, page-level, toast; retry control.
* [ ] Offline / timeout copy.
* [ ] Permission denied vs not found (do not use the same empty illustration).
* [ ] Success: undo if the action is reversible.
* [ ] Partial success (5 of 20 invites failed).

## Type and Space:

* [ ] Tokens only: no one-off `#3B82F6` if the token is `color.action.primary`.
* [ ] Line length ~45–75 chars for body; lists in a 320px column still wrap, not clip.
* [ ] Tabular numbers for money and IDs (`font-variant-numeric: tabular-nums` noted).
* [ ] Truncation: title vs subtitle vs badge; tooltip if truncated.
* [ ] 8px/4px grid: odd 13px paddings are called out as exceptions.

## Interactive Spec:

* [ ] Default, hover, focus-visible, active, disabled, loading, selected, invalid.
* [ ] Keyboard: Tab, Enter, Space, Escape, arrows for the widget type.
* [ ] Cursor: pointer vs default vs not-allowed.
* [ ] Destructive: confirm pattern (modal vs type-the-name) is specified.
* [ ] Toast duration and whether it is assertative (error stays).

## Responsive:

* [ ] Breakpoints named (and match engineering’s CSS).
* [ ] Nav: hamburger vs rail vs bottom bar; focus order.
* [ ] Tables: card stacked vs horizontal scroll vs “columns to hide”.
* [ ] Safe areas (notch, home indicator) if mobile native/webview.
* [ ] Landscape vs portrait if you care (video, camera).

## Content:

* [ ] Final copy or `[WIP copy — owner]`; lorem is labelled.
* [ ] String length: German/Dutch examples pasted for buttons.
* [ ] Numbers: 0, 1, 1,000, 1.5M, negative, empty.
* [ ] Dates: relative vs absolute; timezone note.
* [ ] Empty CTA vs “you don’t have access” copy.

## Assets:

* [ ] SVG for icons; PNG/WebP with 1x/2x if raster; max weight noted.
* [ ] Icon optical alignment (play triangle, etc.) not just bounding box.
* [ ] Favicon / app icon / OG image if this is a new surface.
* [ ] Dark mode assets: invert vs separate file.

## A11y in the File:

* [ ] Contrast on text, icons that convey meaning, and focus ring.
* [ ] Hit target 24px+ (WCAG 2.2) or spacing.
* [ ] Reduced motion variant if animation is essential to understanding.
* [ ] Color is not the only error signal.

## Dev Handoff:

* [ ] Frame names match component names in code.
* [ ] Prototype links for micro-interactions that a still cannot show.
* [ ] Redlines: auto-layout so Inspect is trustworthy; detached instances called out.
* [ ] “Open questions” section at the top of the page, not 40 sticky notes.
* [ ] Version: “Ready for build — 2026-08-21” vs WIP page clearly marked.
* [ ] Changelog of what moved since the last engineering pull.
