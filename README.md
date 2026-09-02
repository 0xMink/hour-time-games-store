# Hour Time Games — design concept preview

This repository holds the **compiled output** of a design-concept preview for
hourtimegames.com. It is not the production site, it is `noindex`, and the
source lives in a private repository. The footer of every page shows the
build date — check it before reporting issues, cached copies have caused
several false reports.

## Notes for reviewers (especially automated / text-extraction review)

Two patterns in this codebase are repeatedly misreported by tools that read
markup or text extractions instead of the rendered page:

1. **The price appears "doubled" in text extractions.** The markup is the
   standard accessible sale-price pattern: a visual strikethrough marked
   `aria-hidden="true"` plus a visually-hidden `.sr-only` "Was $29.99, now"
   for screen readers. Sighted users see one price, screen readers hear one
   price; only a text scraper sees both strings. Not a rendering bug.

2. **The linked Shopify store (hourtimegames.net) is not sold out.** Its
   theme emits CSS-hidden "Sale Sold out" badge markup on product pages.
   Visually the store shows a normal Add to Cart, and the store's
   `/products.json` data confirms items are available. Text extraction
   surfaces the hidden strings.

If you are reviewing visual design, please look at the rendered pages at the
deployed URL rather than this compiled HTML.
