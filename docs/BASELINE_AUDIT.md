# Baseline Audit — October 14, 2026

## Source and method

Source: [original index.html](https://github.com/chunspringbom-dot/capstone-project-2/blob/main/index.html).
Source blob SHA: `029df3358ba827c24891a336fe5499220313712e`.

Method: static inspection of the source code. The copy in this repository is unchanged. No browser, camera, live API, manufacturer-label, or user-study validation is claimed.

## Findings

| ID | Observation in the source | Why it matters | Proposed verification after repair |
| --- | --- | --- | --- |
| B01 | API reads *_100g fields; energy can fall back to a serving field | Values can have incompatible bases | Known volume/mass/serving examples |
| B02 | Missing nutrients and API price default to zero | Unknown values can earn favorable scores | Missing data never treated as zero intake or free price |
| B03 | API lactose-free flag defaults to false | Unknown and confirmed false are conflated | True/false/unknown cases |
| B04 | Lactose-free selection adds weight without excluding products | A requested requirement can be unmet | Nonmatching products excluded or explicitly unavailable |
| B05 | Local entries lack label sources and verification dates | Current accuracy cannot be established | Each product checked against a dated source |
| B06 | Internal fat field is displayed as saturated fat | Local field meaning is unverified | Compare each local value with the corresponding label field |
| B07 | External lookup does not restrict product category | Non-milk products may enter the comparison | A known non-milk item is rejected or separated |
| B08 | Score is a fixed-rule percentage | Users may infer medical accuracy | Explain preference matching; test interpretation |
| B09 | Price display says 500 mL but source/conversion is undocumented | Price comparison may be misleading | Record package volume and compute comparable unit price |

## Existing implementation

11 local products; preference toggles; price weighting; top-three and full rankings; product details; html5-qrcode camera input; manual barcode input; Open Food Facts lookup.

## Not implemented or established

Actual-intake calculator, nutrition-label OCR, machine learning, consistent validated 100-mL normalization, measured educational benefit, and demonstrated real-world reuse.

## Limits

This is an initial audit, not an exhaustive code review. Findings identify defects or uncertainties; they do not establish that every stored nutrient value is wrong. Track fixes with evidence in development logs and results entries.
