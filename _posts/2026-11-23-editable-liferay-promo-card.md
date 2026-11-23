---
title: "Build a reusable, editable promo card in Liferay"
date: 2026-11-23 00:00:00 +0530
description: "Create a Liferay page fragment with an editable heading, summary, and link, then check how it behaves with real content."
---

A promo card is a small way to give content editors control over a page. In this example, the fragment owns the HTML and layout. Editors can update the heading, summary, and destination in the page editor.

## Define the editable fields

Create a fragment and add the following markup in its HTML editor. The example uses an `h2` because the card sits directly below the page heading. Use the heading level that fits where the fragment will be placed.

```html
<div class="office-promo">
  <h2 data-lfr-editable-id="office-title" data-lfr-editable-type="text">
    Singapore office
  </h2>
  <p data-lfr-editable-id="office-summary" data-lfr-editable-type="text">
    Find office hours and contact information.
  </p>
  <a
    href="/web/guest/singapore-office"
    data-lfr-editable-id="office-link"
    data-lfr-editable-type="link"
  >
    View Singapore office details
  </a>
</div>
```

Replace the sample destination with a real page before publishing. Keep editable IDs unique within the fragment and stable after it is in use so existing page edits stay associated with the same fields. [Liferay fragment attributes reference](https://learn.liferay.com/w/dxp/development/developing-page-fragments/reference/fragment-specific-tags-and-attributes-reference)

## Let longer content wrap

Add this to the fragment's CSS editor. The card grows with its contents, and placing the link at the start lets its label wrap inside the available width.

```css
.office-promo {
  display: grid;
  gap: 0.75rem;
  padding: 1rem;
  border: 1px solid currentColor;
  border-radius: 0.5rem;
  overflow-wrap: anywhere;
}

.office-promo > * {
  margin: 0;
}

.office-promo > a {
  justify-self: start;
}
```

## Check both the editor and the published page

1. Add the fragment to a content page twice and give each card different text and a different link.
2. Try the longest heading and link label an editor is likely to enter. Test at a narrow viewport and confirm that both wrap without clipping.
3. Preview the page, tab to each link, and check that focus is visible and that each label identifies its destination.
4. After publishing, open the page as a visitor and follow both links to verify their destinations and access permissions.
