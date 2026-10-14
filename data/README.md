# Product Data and Verification

The current app still uses its original hard-coded catalog in index.html. No verified replacement dataset is included yet.

For each product, create a record using the fields below. Use manufacturer information or a current package label where available. Do not invent values to fill gaps.

## Product record fields

- Product ID and exact name/variant
- Barcode, if verified
- Source URL or authorized label-image path
- Source/access date and verifier
- Package volume and serving volume, in mL where available
- Original nutrition basis: per serving / per 100 mL / per 100 g / other
- Energy and unit; protein; total sugars; added sugars if explicitly available
- Total fat and saturated fat as separate fields
- Calcium and its unit
- Lactose-free status: verified true / verified false / unknown
- Price, currency, package size, store/source, and observation date
- Conversion formula and assumptions
- Differences from the baseline and resolution
- Review status: unverified / checked / needs clarification

## Rules

Missing is not zero. Added sugars cannot be inferred from total sugars alone. Do not assume per 100 g equals per 100 mL; use a documented conversion only when supported. Keep the original values alongside derived values.

For a source expressed per a known volume:
- Per 100 mL = source nutrient amount × 100 / source volume in mL
- Consumed amount = nutrient per 100 mL × consumed volume in mL / 100
- Price per 100 mL = package price × 100 / package volume in mL

If the basis is unknown or incompatible, mark the derived value unavailable.

## Public repository boundary

Store product evidence and non-identifying aggregate research data here. Keep participant identities, consent records, private health information, and identifiable raw feedback outside this public repository.
