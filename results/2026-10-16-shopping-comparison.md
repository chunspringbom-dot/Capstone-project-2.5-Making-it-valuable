# Shopping comparison integration — 2026-10-16

## User goal

Use one shopping platform for as much of the catalog as possible, display actual sale size alongside price per 100 mL, and attach purchase links to preference results.

## Implemented

- SSG.COM selected as primary platform after retailer searches; this is a practical coverage choice, not proof of maximum market coverage.
- Eight direct SSG product pages found. Six observed offers enter price-weighted ranking. Sokpyun is marked sold out by the retrieved page; Maeil Original has a cached base price and remains reference-only. Comfort has only a category listing, nonfat's SSG page was inaccessible, and high-calcium SSG package volume was unresolved; these remain outside price ranking.
- Existing nutrition audit connected via generated catalog, including separate fat fields and Maeil Original trans fat <0.25 g.
- All result cards and product details show price per 100 mL, carton volume, quantity, full sale price, seller/date, shipping qualification and product link when established. Reference offers are labeled; no invented purchase URL for Comfort.
- New links open a separate tab with noopener/noreferrer and do not trigger parent detail navigation.
- Price contribution uses exact item KRW per 100 mL and a linear min/max score over eligible SSG offers. The slider weight is unchanged. When price matters, unsupported prices are excluded rather than converted to zero. With price weight zero, all products can be compared nutritionally.
- Lactose preference filters the candidate list using documented lactose-decomposed/labeled-zero products; no new analytical lactose-threshold claim is made.
- External barcode data no longer masquerades as 100 mL or missing-zero nutrients in this result view; 100g data stays labeled and is excluded from comparable ranking.

## Source observations

All direct source URLs, quantities and observed amounts are in `data/shopping-offers.json`. Observation date is retrieval date, not guarantee of live checkout. Search retrieval can include cached pages. Prices exclude shipping and card, coupon and membership benefits. Pack sizes and seller channels still differ within SSG. Product-line/volume matching is not exhaustive barcode or formulation verification. Price source does not replace the manufacturer's nutrition evidence.

GT was refreshed to KRW 5880 for 900mL x2 (earlier retrieval showed 5480); the latest retrieved page value was used. The cached Maeil Original base price 19900 is preserved as reference and excluded. The lower Traders offer was excluded because the retrieved page marked it sold out.

## Reproduce

1. Update the nutrition audit / shopping offer JSON with evidence.
2. Run `python scripts/build_catalog.py`.
3. Open `index.html` or serve the repository with a static server.
4. With Node, Playwright and its Chromium browser installed, run `node tests/shopping.cjs`.

## Validation

`node tests/shopping-logic.cjs` passed: 11 catalog records, normalized price arithmetic, six eligible price-ranked products, sold-out/missing-price exclusions, safe purchase links, package totals, trans-fat bound, lactose filtering and barcode nutrient basis. These are functional and generated-HTML checks, not browser layout verification. The Playwright browser test was prepared but could not run: Chromium was absent and its download failed. Visual browser verification remains outstanding.

## Remaining work

Resolve the five excluded offers, check address-specific stock/shipping, confirm exact current packages, and evaluate the tool with users. No school-use or health-effectiveness outcome is claimed.
