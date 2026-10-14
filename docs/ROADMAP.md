# Improvement Roadmap

Status labels: Planned / In progress / Implemented / Verified. Implementation alone does not mean verification.

| Priority | Work | Status | Completion evidence |
| --- | --- | --- | --- |
| P0 | Audit all 11 local products against sources | Planned | Source/date/unit records and discrepancy list |
| P0 | Replace missing-value defaults with explicit unknowns | Planned | Missing sugar/fat/price cannot earn favorable points |
| P0 | Resolve per-100g, per-serving, and per-100mL bases | Planned | Worked conversion cases; incompatible units excluded |
| P0 | Separate lactose-free requirement from scoring | Planned | Nonmatching/unknown products handled explicitly |
| P0 | Verify saturated-fat mapping and milk-only lookup scope | Planned | Label checks and non-milk lookup cases |
| P1 | Explain scoring and rename misleading percentage language | Planned | Published rules and manually checked examples |
| P1 | Add actual-intake calculator | Planned | Checked calculations for different volumes and unknown values |
| P1 | Add short nutrition explanations | Planned | Source-linked content reviewed for accuracy |
| P2 | Finalize and conduct comprehension pilot | Planned | Protocol frozen before collection; aggregate results |
| P3 | Test school access and voluntary reuse | Planned | Usage records, failures, feedback, and maintenance assessment |

## First working session

Choose one local milk product. Obtain its current nutrition label and package size. Record the source, date, units, price basis, and differences from the code. Use that example to settle the data fields before auditing the remaining products.

## What comes later

Consider OCR, more product categories, international data, or machine learning only after identifying a user problem that the simpler tool cannot solve.

## Decisions

Record scope changes in the development log, including the reason and evidence. Do not mark a stage complete merely because a feature looks finished.
