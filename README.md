# Capstone Project 2.5 — Making It Valuable
## Improving a milk-comparison prototype through trustworthy data and user evidence

**Status: baseline imported; improvement and evaluation not yet completed.**

This repository continues [Capstone Project 2](https://github.com/chunspringbom-dot/capstone-project-2). The original project moved from displaying milk information to preference-based ranking after team discussion and teacher feedback. Project 2.5 focuses on making that prototype accurate, understandable, and useful in a school setting.

### Our guiding question

**Can a verified milk-comparison tool help students interpret nutrition labels and compare products more accurately than labels alone?**

This is a proposed evaluation question, not a finding. The app supports nutrition literacy and stated preferences; it does not diagnose conditions or provide clinically validated dietary advice.

### Start here

| Space | Purpose |
| --- | --- |
| [Roadmap](docs/ROADMAP.md) | Ordered improvements and evidence required to finish each stage |
| [Baseline audit](docs/BASELINE_AUDIT.md) | What the original code does and what needs correction |
| [Development log](development/README.md) | Problems, decisions, changes, tests, and personal learning |
| [Evaluation protocol](evaluation/PROTOCOL.md) | Plan the comparison before collecting data |
| [Results](results/README.md) | Report technical checks and study findings, including negative results |
| [Real-world use](usage/README.md) | Record where, why, and how the tool was actually used |
| [Data documentation](data/README.md) | Verify product sources, units, missing information, and prices |
| [Contributions](docs/CONTRIBUTIONS.md) | Record individual work and AI assistance honestly |

### What exists today

The imported [index.html](index.html) contains an 11-product local catalog, preference controls, hand-written weighted rankings, product details, and camera/manual barcode lookup through Open Food Facts. Actual-intake calculation, OCR, machine learning, and consistent unit normalization are not implemented.

The imported code is an **unmodified baseline**, including known defects. Code inspection has been performed; browser operation, camera behavior, product accuracy, and educational effectiveness have not been verified in this phase. No deployment of this repository is claimed.

### Why another phase?

A useful nutrition tool needs more than a ranking. It needs reliable input data, transparent rules, and evidence that users understand the output.

The baseline audit found mixed measurement bases, missing values treated as zero, incomplete lactose-free handling, and unverified nutrient/price sources. These are the first priorities.

### Planned improvements

1. Verify the existing product catalog and preserve unknown values.
2. Make units and price bases explicit; implement supported volume normalization.
3. Separate required conditions from optional preferences and explain score components.
4. Add an actual-intake calculator using verified volume-based values.
5. Run a small, supervised nutrition-label comprehension pilot.
6. Record voluntary real-world use and revise the tool based on evidence.

OCR, larger international catalogs, and AI models remain later possibilities, conditional on a demonstrated need.

### Biology and health-literacy focus

Document the sources and reasoning behind distinctions such as total versus added sugars, lactose digestion versus milk-protein allergy, and total versus saturated fat. A preference score is not a medical suitability percentage. Do not treat lactose-free dairy as an allergy-safe substitute.

Background sources:
- [FDA: Added Sugars](https://www.fda.gov/food/nutrition-facts-label/added-sugars-nutrition-facts-label)
- [NIDDK: Lactose Intolerance](https://www.niddk.nih.gov/health-information/digestive-diseases/lactose-intolerance/definition-facts)

### Evidence status

| Claim | Current evidence |
| --- | --- |
| A prototype exists | Imported source code |
| Known implementation problems identified | Static code audit |
| Problems fixed | Not yet demonstrated |
| Product data verified | Not yet completed |
| Students understand labels better | Not measured |
| Students reuse the tool | Not measured |
| Health outcomes improve | Not studied; outside the initial pilot |

### Working routine

After each work session, copy the development-log template and record what actually happened. Link changes to a commit, link checks to a results entry, and link user observations to a usage entry. Update this README only when the evidence supports a new status.

Write project records in English. Keep plans, completed work, observations, and interpretations separate.

### Running the baseline

The app is a single HTML/CSS/JavaScript file. Serve it through a static web server. The camera requires browser permission and an appropriate secure context; the scanner library, fonts, and product API require network access.

### Origin

Imported on October 14, 2026 from the original repository's `index.html`, blob SHA `029df3358ba827c24891a336fe5499220313712e`. See the baseline audit for limitations. This repository starts the improvement phase rather than claiming the original prototype has already been validated.
