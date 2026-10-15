# Product nutrients — per 100 mL

**All values below are per 100 mL (100mL 기준).** Total fat, saturated fat and trans fat are separate label fields; do not add them together. “Unknown” is not zero. Values reflect manufacturer web tables and user-supplied label images reviewed on October 15, 2026, not laboratory measurements. A label value of 0 g is preserved as a label value.

| Product | Energy (kcal) | Sugars (g) | Total fat (g) | Saturated fat (g) | Trans fat (g) | Protein (g) | Calcium (mg) | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 서울우유 나100% | 70 | 5 | 4 | 2.5 | 0 | 3 | 100 | S01 |
| 남양 맛있는우유 GT | 65 | 4.5 | 4 | 2.5 | 0 | 3 | 100 | S17 |
| 매일우유 오리지널 3.4% (200mL 팩) | 60 | 4.5 | 3.4 | 2 | <0.25 | 3 | 100 | S14 |
| 나100% 저지방 | 40 | 5 | 1 | 0.6 | 0 | 3 | 100 | S02 |
| 내 속이 편안한 우유 | 65 | 3.5 | 4 | 2.5 | 0 | 3 | 100 | S03 |
| 서울우유 무지방 | 30 | 5 | 0 | 0 | 0 | 3 | 100 | S04 |
| 고단백저지방 서울우유 | 50 | 5 | 1 | 0.6 | 0 | 5.5 | 180 | S05 |
| 속편한우유 저지방 | 40 | 5 | 1 | 0.6 | 0 | 3 | 100 | S06 |
| 서울우유 로얄 저지밀크 (구 브라운; 사용자 확인) | 80 | 5 | 5 | 3.3 | 0 | 4 | 140 | S11, S15 |
| 뼈에 쏙쏙 고칼슘우유 (930mL) | 70 | 5 | 4 | 2.5 | 0 | 3 | 225 | S18 |
| 소화가 잘되는 우유 단백질 (930mL) | 55 | 3 | 3.4 | 2.2 | 0 | 5 | 190 | S16 |

## Source and conversion rules

Source URLs, dates, original label tables and baseline values are preserved in the [structured audit](product-verification-2026-10-15.json). The [audit report](../results/2026-10-15-product-data-audit.md) explains verification status and exact-product limitations.

- Volume-based conversion: amount per 100 mL = source amount × 100 / source volume in mL.
- Do not convert 100 g to 100 mL without a supported density or volume basis.
- Maeil Original 3.4% 200-mL carton: [label evidence](evidence/maeil-original-3.4-200ml-label.png), divided by two. Trans fat <0.25 g per 100 mL is stored as a structured bound; it is not zero.
- Royal Jersey uses the current manufacturer table. The former Brown name and rename are user-reported (S15).
- Prices are monetary observations with their own package volumes, not nutrition units. The existing app has not yet been connected to this standardized dataset.

## Follow-up label evidence

- [Maeil Protein label](evidence/maeil-digest-protein-930ml-label.png): product name confirmed by the user; printed basis is 100 mL.
- [Namyang GT label](evidence/namyang-gt-label.png): 200-mL values divided by two.
- [High-calcium label](evidence/seoul-high-calcium-930ml-label.png): select the shown 930-mL product and its explicit 100-mL table (70 kcal; trans fat 0 g). Earlier conflicting tables remain in JSON as history.
- All 11 selected products now have evidence for the seven compared nutrient fields, including a bound instead of an exact trans-fat amount for Maeil Original. This is label/source verification, not laboratory validation or proof of current packaging for every SKU.
