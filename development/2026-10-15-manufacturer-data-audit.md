# 2026-10-15 — First manufacturer-source data audit

## Request and purpose

The user asked ChatGPT to search for the product data and verify it. The goal was to establish what can be supported before changing the recommendation logic.

## Work completed

- Reviewed all 11 baseline product records against manufacturer-source search results and available tables.
- Added a structured audit preserving baseline values, accepted evidence, source dates, unknowns and unresolved leads.
- Recorded six five-field nutrient matches, one measurement-basis clarification and four unresolved nutrient records.
- Captured one official, dated 930-mL home-delivery price observation, separately from the unverified baseline prices.
- Updated the project overview and record indexes.

See [results and limits](../results/2026-10-15-product-data-audit.md) and the [structured audit](../data/product-verification-2026-10-15.json).

## Decisions and reasoning

- Preserve the original app during this evidence-gathering step. Its scores still include undocumented data.
- Do not relabel all baseline numbers as wrong: six profiles agree with official tables.
- Name total and saturated fat separately in the future schema; confirmed baseline fat values correspond to saturated fat.
- Retain both high-calcium energy displays and their original bases instead of forcing an apparent correction.
- Leave unsupported values unknown. A related product or unreadable image does not verify an exact variant.

## Failed or incomplete retrieval

Some Seoul Milk requests timed out or returned gateway errors; alternate official paths retrieved most relevant tables. Namyang's official lead did not yield a readable exact panel. The Maeil Protein listing linked to a generic/low-fat graphic rather than a usable exact-product panel. Searches found Royal Jersey rather than a confirmed Brown Jersey match. Maeil has several variants, and the baseline does not identify its package. None of those gaps was filled using guessed values or third-party nutrition databases.

## Validation and contribution

Record consistency, arithmetic and Markdown links were checked; app source remained unchanged. ChatGPT performed this desk audit and documentation. A human second review remains outstanding. No experiment or school use took place.

## Next step

Implement explicit units and missing-value handling using the documented subset; resolve the remaining exact variants before adding them as verified choices. Prices need a consistent purchasing context.

## User-requested fat fields and unit standardization

Added separate total-fat, saturated-fat and trans-fat fields; standardized all canonical profiles to 100 mL with explicit nutrient units; added a readable comparison table. Retained unknowns and original source bases. Preserved the high-calcium trans-fat bound rather than converting it to zero. The user explicitly authorized pushing these changes to the specified GitHub repository. App integration remains pending.
