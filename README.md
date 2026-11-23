# Dycem Team Gear

Buildless responsive apparel portal. Serve `dist/` as a static site.

## Catalog
31 styles: the 25 approved SanMar options plus six retained Heavy Press styles. The existing LST340 RacerMesh entry was updated to SanMar rather than duplicated. Departments cover polos, tees, hoodies, athletic/fleece quarter zips, jackets, vests, and shirts/blouses. Men's/women's and black/white filters combine with category and search.

`dist/products.js` contains supplier codes, source URLs, actual selectable size ranges, supplier body measurement charts in inches, product details and local product photographs. SanMar pages and photos were retrieved on 2026-11-23. Generic supplier size charts are limited to each product's offered sizes. Black-only garments have no white selector. Mercer+Mettle blouses are black only because Ivory Chiffon is outside the approved palette. Stock and prices are not live.

## Item logo selection
Every detail view lets the rep select Dycem or Dycem Data Centers before adding to the bag. Standard Dycem is red on both black and white fabric, always on the wearer’s left chest. Existing bag items are normalized to red for the standard logo. The supplied full-color Data Centers artwork uses a white wordmark on black and a dark wordmark on white. Both logos remain on the wearer's left chest. Photo overlays are approximate decoration previews.

Logo selections persist per bag item, can be edited in the bag, and carry into checkout and request exports. Different logo choices for the same garment/color/size remain separate lines. Existing bag items default to standard Dycem. Supplier IDs and source URLs are exported for future backend mapping.

## Integration boundary
This remains a frontend prototype. Bag and demo requests persist in browser localStorage. No email, manager notification, payment or supplier order is sent. The UI states this explicitly. `submitOrder` and `saveRequest` in `dist/app.js` are the API integration points. Requests contain `demo: true` and `submitted: false`. Live operation needs authenticated reps, durable request storage, manager approval routing and supplier integration.

## Verification
Syntax checks; catalog validation for IDs, image assets, permitted colors, size chart alignment and complete expected styles; browser review of category/fit filters, product details, both logo previews, separate bag lines and checkout summaries.

## Vercel deployment

The site is ready to import from a private GitHub repository. `vercel.json` serves `dist/` with no install or build step and the Other framework preset. Keep the repository root as the project root. Subsequent commits to the production branch can deploy through Vercel’s GitHub integration.

The ChatGPT Sites login is provided by its hosting platform, not this static code. Configure appropriate access protection in Vercel before sharing this internal portal. Local browser bags and demo requests are tied to their site origin and do not transfer between hosts. Approval routing remains a frontend demo until a backend is connected.
