# Mr. Clay's Lawn Care

Static marketing site for Mr. Clay's Lawn Care / Mr. Clay's Landscaping.

## Pricing business rules

- Essential Care is J$15,000 per month for 2 lawn care visits.
- New Lawn Development is a standalone J$50,000 plan with Consultation/Inspection included.
- New Lawn Development is built as Lawn Care × 4 visits per month.
- 3 and 4 visit plans include Fertilizer Treatment and Watering on visit.
- Hedging includes Pesticide Treatment at no added charge.
- Lawn Care includes Weed Control & Removal at no added charge.
- New Lawn Development includes Topsoil Treatment at no added charge.
- Treatments may also have standalone charges when not included by the selected plan.

## Page order

The main content order is:

1. Services
2. New Lawns
3. Pricing
4. Plans
5. Book Now

New Lawns and Pricing intentionally appear before the custom plan builder.

## UI logic

- The reduced desktop left-menu label uses `Plans` instead of `Custom Plans` to avoid cutoff in the narrow rail.
- Included treatments are highlighted in the plan builder.
- The plan preview separates paid charges from included no-charge treatments.

## Deployment

- `.nojekyll` is included so GitHub Pages serves this as a plain static site and does not try to process the project through Jekyll.
