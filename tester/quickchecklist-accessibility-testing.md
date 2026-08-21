## Keyboard (do this before the screen reader):

* [ ] Tab order follows visual order; no unexplained skips or traps outside a dialog.
* [ ] Focus ring is visible on dark and light backgrounds (not `outline: none` without a replacement).
* [ ] Custom dropdown/datepicker/tabs are operable with arrows, Enter, Escape, Home/End as expected.
* [ ] Modal: focus moves inside, Tab cycles, Escape closes, focus returns to the opener.
* [ ] Toast/alert does not steal focus unless it is an error that must be corrected now.
* [ ] Skip link is first focusable and lands on main, not a duplicate nav.
* [ ] “Back to top” and sticky headers do not hide focused controls (scroll-margin / offset).
* [ ] Disabled controls are not in tab order unless the pattern requires an explanation.

## Screen Reader (pick NVDA+Firefox or VoiceOver+Safari; do not only use ChromeVox):

* [ ] Page title changes on client-side route change (SPA).
* [ ] Landmarks: one `main`, nav labelled if multiple (`aria-label="Footer"` vs `"Primary"`).
* [ ] Headings: a clear page title (usually one visible h1). Do not skip levels only to get a smaller font (`h3` as styling).
* [ ] Buttons are `<button>` or `role="button"` with Enter/Space; a `<div onclick>` is called out as a defect.
* [ ] Icon-only buttons have an accessible name (`aria-label` / visually hidden text), not only a tooltip.
* [ ] Images: meaningful alt; decorative `alt=""`; charts have a text alternative, not `alt="chart"`.
* [ ] Live regions: form errors and cart updates are announced (`aria-live` / `role="alert"`) without being too noisy.
* [ ] iframes have a title.
* [ ] `aria-*` is not wrong: `aria-hidden="true"` is not on a focused element; duplicate names are not on the same control.

## Forms:

* [ ] `<label for>` matches `id`; placeholder is not the only label.
* [ ] Required and format (date, password rules) are in text, not color-only.
* [ ] Error is associated with `aria-describedby` / `aria-invalid` on the field, not only a banner at the top.
* [ ] Autocomplete attributes on name, email, address, cc-* if you collect them (WCAG 1.3.5).
* [ ] Timeout: user is warned and can extend; posted data is not silently dropped.
* [ ] CAPTCHA has a non-visual alternative.

## Contrast and Visual:

* [ ] Body text ≥ 4.5:1; large text ≥ 3:1; UI components/icons that convey state ≥ 3:1 (WCAG 1.4.11).
* [ ] Placeholder and disabled text are not the only way to know the field exists.
* [ ] Focus / hover / selected is not color-only (also shape, icon, or text).
* [ ] Text in images of text is avoided for essential copy.
* [ ] 200% zoom (or 400% reflow at 320 CSS px): no overlapping, no clipped controls, two-direction scroll only if a data table/tool requires it.
* [ ] Target size: 24px (WCAG 2.2) or equivalent spacing; adjacent icon buttons are not 16×16 with no gap.

## Motion, Media, Seizure:

* [ ] Nothing flashes more than 3 times per second.
* [ ] Autoplay video is paused/muted; captions exist for speech; audio description or transcript if visuals are required.
* [ ] `prefers-reduced-motion`: parallax and large loops are reduced or off.
* [ ] Carousel does not rotate without a pause control.

## Language and Cognitive:

* [ ] `lang` on `<html>` and on passages in another language.
* [ ] Link text is unique in context (“Read more” needs extra hidden text for the article title).
* [ ] Errors say how to fix, not only “Invalid”.

## SPA / Dynamic:

* [ ] Route change announces the new page (title + focus to heading or `h1`).
* [ ] Infinite scroll has a keyboard-accessible “load more” or pagination alternative.
* [ ] Drag-and-drop has a keyboard alternative.

## Record:

* [ ] Browser, AT version, OS, and URL for each fail.
* [ ] Map fails to WCAG SC (e.g. 2.4.7, 1.4.3, 4.1.2) so devs do not argue “but it works for me”.
