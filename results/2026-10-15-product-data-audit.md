# Manufacturer-source product data audit — October 15, 2026

## Follow-up: user product clarification and label image

This update supersedes the original unresolved Maeil and Brown rows below. The original comparison is retained as audit history.

- Maeil: user corrected 3.6% to **Original 3.4%, 200 mL** and supplied a readable label image (S14). Per 100 mL: 60 kcal, sugars 4.5 g, total fat 3.4 g, saturated fat 2 g, protein 3 g, calcium 100 mg; trans fat **<0.25 g**. The strict bound is stored separately from exact numeric values. Baseline estimates are preserved, not reused.
- Royal Jersey: user confirmed Seoul Milk and reported the Brown-to-Royal rename (S15). The current manufacturer's Royal Jersey 750-mL page was retrieved successfully (S11). Per 100 mL: 80 kcal, sugars 5 g, total fat 5 g, saturated fat 3.3 g, trans fat 0 g, protein 4 g, calcium 140 mg. The rename history is user-reported rather than independently established.
- Remaining nutrition gaps: GT (exact panel missing), Maeil Protein (exact panel missing), high-calcium milk (energy and trans-fat package/basis discrepancy).
- All 11 baseline prices remain unverified; barcodes and added sugars remain unknown. Residual lactose thresholds have not been established.
- The [current comparison](../data/NUTRIENTS_PER_100ML.md) and structured JSON reflect this follow-up. App integration is still pending.

## Original audit outcome

Reviewed all 11 baseline records. Six match all five stored nutrient values against manufacturer tables; one requires package/basis clarification; four lack sufficient exact-variant nutrient evidence. **This does not mean that six complete product records are verified:** prices, barcodes, added sugars, and residual lactose thresholds remain unverified unless explicitly stated.

The app is unchanged. This audit creates a documented input for the next implementation step, not a verified production catalog or an effectiveness result.

## Method and reproducible record

Compared the `DB` array in baseline commit `3d1fcafd4eb3de17a0bbc839c92907bfaf912f70` with manufacturer product pages and the official Maeil shop on October 15, 2026. Used web search and retrieved page tables. Search results were checked with page retrieval where possible; some requests timed out. S01 and S06 nutrition tables were available in full through the search retrieval. No physical package, barcode, laboratory sample or student was inspected.

The [structured record](../data/product-verification-2026-10-15.json) preserves every baseline value, official values accepted, original bases, source URLs, access dates, comparisons, unknowns and unresolved leads. Source IDs below refer to that record. A source URL and date are a traceable observation, not an archived copy or a guarantee that a future page will be unchanged.

## Comparison

In the next table, values are **kcal / total sugars g / saturated fat g / protein g / calcium mg per 100 mL**. Baseline `fat` is compared with saturated fat, consistent with the displayed field and API mapping. Total fat and trans fat are separately recorded in JSON and the [uniform per-100-mL comparison](../data/NUTRIENTS_PER_100ML.md).

| Baseline ID / name | Official reference values | Finding | Source |
| --- | --- | --- | --- |
| seoulna / 서울우유 나100% | 70 / 5 / 2.5 / 3 / 100 | All five match | S01 |
| namyang / 남양 맛있는우유 GT | Unknown | Exact manufacturer nutrition panel not obtained | S12 (lead only) |
| maeil / 매일우유 | Unknown | Exact package/variant not established; brand pages alone insufficient | S09, S10 |
| lowfat / 나100% 저지방 | 40 / 5 / 0.6 / 3 / 100 | All five match | S02 |
| comfort / 내 속이 편안한 우유 | 65 / 3.5 / 2.5 / 3 / 100 | All five match; lactose-decomposed category stated | S03 |
| nonfat / 서울우유 무지방 | 30 / 5 / 0 / 3 / 100 | All five match plain nonfat 900-mL product | S04 |
| hipro / 고단백저지방 서울우유 | 50 / 5 / 0.6 / 5.5 / 180 | All five match | S05 |
| sokpyun / 속편한우유 저지방 | 40 / 5 / 0.6 / 3 / 100 | All five match; enzymatic lactose breakdown stated | S06 |
| brown / 브라운 저지밀크 | Unknown | Related Royal Jersey page is not proof of identical product | S11 (related-product lead) |
| calcium / 뼈에 쏙쏙 고칼슘우유 | 67.5 / 5 / 2.5 / 3 / 225 from 200-mL table; separate 100-mL table gives 70 kcal | Four fields consistent across both bases; energy requires variant/basis resolution | S07 |
| digest / 소화가 잘되는 우유 단백질 | Unknown | Exact 930-mL listing and price obtained; nutrient panel not verified | S08 |

### Finding 1: clarify fat naming; do not replace saturated fat with total fat

For Na100%, the manufacturer lists total fat 4 g and saturated fat 2.5 g per 100 mL. The baseline stores 2.5 and displays saturated fat. This is a naming/traceability issue, not evidence that 2.5 should become 4. All six matched rows support the saturated-fat interpretation. A future schema should use `total_fat_g` and `saturated_fat_g` separately. We cannot generalize verification to the four unresolved rows.

The six matching profiles also have official total-fat and trans-fat label values. Their trans fat is labeled 0 g per 100 mL. The canonical profile for each unresolved product has explicit null fields rather than an absent schema.

### Finding 2: retain the high-calcium milk's two bases

S07 lists 135 kcal, sugars 10 g, saturated fat 5 g, protein 6 g and calcium 450 mg per 200 mL. Dividing by two gives the baseline values, including 67.5 kcal. The same page separately lists 70 kcal per 100 mL, with the other four fields unchanged after normalization. Package sizes include 200 and 930 mL. The cause may involve package variants or labeling/rounding, but it was not established. Do not call the baseline energy wrong, average the values, or assign the second table to 930 mL without further evidence.

### Finding 3: nonfat products are not interchangeable

S04 plain nonfat milk has calcium 100 mg per 100 mL. S13 nonfat-and-calcium milk has 120 mg. The baseline matches S04. A search for just “nonfat milk” could select the wrong product and introduce an error during apparent correction.

### Finding 4: separate lactose processing from a verified lactose threshold

S03 and S06 explicitly identify lactose-decomposed milk; S06 describes enzymatic breakdown rather than removal. This supports documenting processing, but we did not establish residual lactose concentrations or a specific lactose-free labeling threshold. The structured dataset leaves the strict `lactose_free_claim` field unknown instead of interpreting a missing statement as false. Existing app booleans remain baseline claims.

### Finding 5: baseline prices remain unverified

None of the 11 baseline prices has a recorded store, observation date, purchase volume or original conversion. A 500-mL display label does not prove those inputs were collected on that basis.

For the exact S08 listing, the official home-delivery shop displays KRW 4,500 for 930 mL. Arithmetic gives:

- KRW 4,500 × 100 / 930 = **483.87 per 100 mL**.
- KRW 4,500 × 500 / 930 = **2,419.35 per 500 mL equivalent**.

That is a dated channel-specific observation, not a universal price, a purchasable 500-mL package, or proof that the baseline 2,085 was wrong. Shipping cost and ordering availability were not confirmed. Do not mix this single official-delivery observation with ten undocumented prices in a supposedly fair ranking.

### Standardization update requested by the user

All canonical nutrient objects now use 100 mL with separate total, saturated and trans fat in grams. Original tables retain their source volume. High-calcium milk keeps energy and trans fat unknown in the canonical profile: its 200-mL trans-fat label is <0.5 g, which converts to <0.25 g per 100 mL, while the separate 100-mL table lists 0 g. A less-than bound is not recorded as zero or as an exact amount. The four other unresolved profiles remain null throughout.

## Limits and next implementation decisions

1. Use the six matched nutrient profiles as the initial documented subset, preserving source IDs and volume basis. Do not mark entire records verified.
2. Keep the high-calcium product on hold until the actual package/variant is selected.
3. Resolve exact variants and obtain readable manufacturer/package panels for GT, Maeil, Brown Jersey and Maeil Protein; leave unavailable fields null meanwhile.
4. Handle missing data in scoring before connecting this JSON to the app. Passing null through JavaScript numeric comparisons can still earn favorable points; JSON null alone is not a scoring fix.
5. Collect comparable price observations for the school purchasing context. Do not use 0 as unknown.
6. Keep API normalization, required-condition filtering, score explanations and user evaluation as separate unfinished tasks.

## Verification performed on this deliverable

Checked JSON parsing, coverage of all 11 baseline IDs, exact preservation of baseline fields, all 30 accepted comparisons, both high-calcium bases, price-conversion arithmetic, and relative Markdown links. Confirmed `index.html` is unchanged. These checks validate record consistency; they do not independently validate the manufacturer's claims or measure educational benefit.

## Attribution

The user requested external data verification. ChatGPT performed web retrieval, comparison and English documentation. Human second review and the user's own interpretation have not yet been recorded. No participant-study or real-world-use outcome is claimed.
