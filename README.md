# TankFlare Community

Welcome to the public community space for **TankFlare**.

TankFlare is an aquarium planning and care tool focused on freshwater fishkeeping, stocking checks, species care, plant compatibility, disease guidance, symptom triage, and many, many more features.

This repository is **not** the TankFlare application source code. The main TankFlare app is currently private. This repo exists so fishkeepers, hobbyists, breeders, plant keepers, and experienced aquarists can help improve TankFlare through public feedback, corrections, suggestions, and source-backed contributions.

## What This Repo Is For

Use this repository to contribute:

- Species care corrections
- Plant care corrections
- Disease and symptom guidance corrections
- Stocking checker disagreement reports
- Missing fish, shrimp, snail, or plant requests
- Missing disease or condition requests
- Bug reports from the public website
- Feature requests
- Usability feedback
- Source-backed improvements to TankFlare content
- Real-world aquarium experience that can improve checker behavior

The goal is to make TankFlare more accurate, useful, practical, and transparent without requiring the main application code to be public yet.

## What This Repo Is Not

This repository does **not** contain:

- TankFlare application source code
- Internal checker logic
- Private datasets
- Model training code
- Production infrastructure
- Private prompts
- User data
- Database exports
- Proprietary app internals

Please do not ask for access to the private source repo here. Public issues and contribution files are the current contribution path.

## Why This Exists

Aquarium advice is messy.

Different keepers often disagree because real tanks vary by:

- Tank age
- Filtration
- Maintenance routine
- Plant density
- Stocking history
- Fish age and size
- Water parameters
- Local strains
- Individual fish temperament
- Food availability
- Oxygenation
- Flow
- Quarantine practices

TankFlare tries to give useful planning guidance, but no automated checker can be perfect. This repo gives the aquarium community a public place to point out mistakes, explain edge cases, and submit improvements.

## Ways To Contribute

There are two main contribution paths:

## 1. Open an Issue

Issues are best for:

- "This result seems wrong"
- "This species page has a mistake"
- "This disease page is missing something"
- "TankFlare should support this feature"
- "I found a bug"
- "This page is confusing"
- "Please add this species"
- "Please add this disease"
- "This checker explanation is too harsh, too permissive, or unclear"

Issues are discussion-first. They do not need to be perfect. If you noticed something wrong, open an issue and explain what happened.

## 2. Open a Pull Request

Pull requests are best for structured corrections.

Since the main app code is private, PRs in this repo should usually add or edit contribution files, not application code.

Examples:

```txt
corrections/species/otocinclus-algae-eater-care.md
corrections/diseases/ich-treatment-temperature-note.md
corrections/checker-reports/75-gallon-roseline-rainbowfish-load.md
requests/species/celestial-pearl-danio.md
requests/diseases/columnaris.md
```

A pull request here is a reviewable correction packet. If accepted, the TankFlare maintainer may manually import the change into the private TankFlare app, database, or content system.

## Good Contributions

A good contribution is specific, practical, and explains why the current TankFlare information should change.

Good examples:

- "Otocinclus should be marked as mature-tank preferred because they often rely on biofilm and can starve in new tanks."
- "This stocking report over-penalizes raw animal count because it treats Amano shrimp the same as active midwater fish."
- "This disease page should distinguish ich from epistylis because raising temperature can be risky if the diagnosis is wrong."
- "This species should mention high oxygen needs because it is commonly kept in high-flow river-style setups."
- "This symptom checker result should ask about ammonia and nitrite before suggesting medication."

Less useful examples:

- "This is wrong."
- "Bad advice."
- "Everyone knows this."
- "Just Google it."
- "My fish were fine, so the checker is bad."

Personal experience is welcome, but please explain the tank conditions.

## Helpful Context For Checker Disagreements

If you disagree with a stocking checker result, please include as much of this as possible:

- Tank size
- Tank age
- Filter type or flow rate
- Plant level
- Current stock
- Wanted stock
- Temperature
- pH, GH, and KH if known
- Ammonia, nitrite, and nitrate if known
- Maintenance routine
- Whether the tank is heavily planted
- Whether fish are juveniles or adults
- What TankFlare said
- What you think it should have said
- Why

Example:

```md
Tank size: 75 gallons

Stock:
- 7 Roseline Sharks
- 15 Turquoise Rainbowfish
- 12 Bronze Corydoras
- 8 Otocinclus
- 16 Amano Shrimp

TankFlare result:
Risky, 55/100

Issue:
The risk level seems reasonable, but the explanation says "58 fish" as if all animals contribute equally.

Suggested wording:
This is a heavy community stocking mainly because the plan combines many active midwater fish with a large cleanup/bottom crew. It may work in a mature, well-filtered planted tank, but the margin is thin.
```

## Helpful Context For Species Corrections

For species corrections, please include:

- Species name
- Page or field being corrected
- Current TankFlare claim, if known
- Suggested replacement
- Reasoning
- Sources, if available
- Whether your claim is based on personal experience, published sources, or both

Example:

```md
Species: Otocinclus Algae Eater

Current issue:
The care guidance does not strongly enough emphasize mature tanks.

Suggested change:
Mention that Otocinclus usually do best in mature aquariums with established biofilm and stable water quality. They should not usually be added to brand-new tanks.

Reason:
Many losses happen from starvation or instability after being added to immature tanks.

Evidence:
- Personal experience
- Common breeder/importer guidance
- Source links here
```

## Helpful Context For Plant Corrections

For plant corrections, please include:

- Plant name
- Current TankFlare claim, if known
- Suggested replacement
- Tank context where the correction matters
- Whether the plant is usually low tech, high tech, floating, rooted, epiphytic, carpeting, foreground, midground, or background
- Light, CO2, fertilizer, substrate, or trimming notes if relevant
- Sources, if available

Examples of useful plant corrections:

- "This plant is listed as easy, but it usually melts badly in unstable new tanks."
- "This plant should be marked as a root feeder."
- "This plant can shade small foreground plants if it is not trimmed."
- "This plant should not be recommended as a carpeting plant in low light."

## Helpful Context For Disease Corrections

For disease or symptom corrections, please include:

- Disease or condition name
- Current TankFlare claim, if known
- Suggested correction
- Symptoms involved
- Risk of misdiagnosis
- Treatment notes
- Whether the correction is about freshwater, saltwater, ponds, or a specific species group
- Sources

Disease guidance is especially sensitive. Please avoid presenting uncertain diagnoses as guaranteed. TankFlare should help users think clearly, not over-prescribe.

## Source Guidelines

Sources are encouraged, but not all contributions require formal citations.

Good sources include:

- Veterinary or aquatic health references
- University extension resources
- Aquarium science articles
- Experienced breeder documentation
- Manufacturer instructions for medications or test kits
- Well-documented hobbyist writeups
- Multiple independent care references

Please do not copy large sections of text from other websites, books, apps, databases, or care sheets. Summarize in your own words and link to the source.

## Do Not Submit Copyrighted Dumps

Please do not submit:

- Full copied care sheets
- Scraped database rows
- Full book excerpts
- Paid app content
- Private forum posts without permission
- AI-generated bulk species pages with no review
- Copied disease articles
- Copyrighted photos you do not own

Short quotes for discussion may be okay, but original summaries are strongly preferred.

## Contribution Rights

By opening an issue, discussion, or pull request, you agree that TankFlare may use, edit, publish, adapt, summarize, and incorporate your contribution into TankFlare products, data, docs, tools, websites, models, and services.

Please only submit content you created yourself or are allowed to share.

This helps keep contribution rights clear while allowing accepted corrections to be imported into the main TankFlare app.

## Public Discussion Expectations

Be direct, but be useful.

Aquarium care has disagreements. That is fine. Please focus on:

- Evidence
- Tank context
- Practical risk
- Clear reasoning
- Better wording
- Better user outcomes

Avoid:

- Personal attacks
- Gatekeeping
- Mocking beginners
- Vendor drama
- Unsupported absolutes
- Dangerous treatment claims without context

## How Accepted Contributions Are Used

Accepted contributions may be used to improve:

- Species pages
- Plant pages
- Disease pages
- Symptom checker logic
- Stocking checker explanations
- Tank report wording
- Search results
- Advisor responses
- Educational content
- Internal review notes
- Future public documentation

Because the main app is private, accepted PRs may not directly change production. A maintainer may manually import the accepted change into the private TankFlare codebase or content system.

## Contribution Status Labels

Issues and PRs may use labels like:

- `needs-review`
- `needs-source`
- `accepted`
- `imported`
- `declined`
- `duplicate`
- `checker-feedback`
- `species-correction`
- `plant-correction`
- `disease-correction`
- `feature-request`
- `bug`
- `good-first-issue`

The most important label is usually `imported`, which means the suggestion has been brought into TankFlare itself.

## Common Contribution Types

## Species Correction

Use this when a fish, shrimp, snail, or other aquarium animal has incorrect or incomplete care information.

Examples:

- Minimum tank size
- Group size
- Temperature range
- pH range
- Adult size
- Temperament
- Fin-nipping risk
- Shrimp safety
- Oxygen needs
- Flow preference
- Diet difficulty
- Mature tank requirement

## Plant Correction

Use this when a plant page or plant compatibility result needs improvement.

Examples:

- Light requirement
- CO2 requirement
- Growth rate
- Placement
- Difficulty
- Floating vs rooted behavior
- Fish compatibility
- Melting risk
- Nutrient demand

## Disease Correction

Use this when disease information is incomplete, misleading, or missing nuance.

Examples:

- Similar-looking diseases
- Treatment risk
- Urgency level
- Water quality first steps
- Medication warnings
- Quarantine advice
- When to avoid a treatment

## Checker Report Disagreement

Use this when the stocking checker result is not quite right.

Examples:

- Score too harsh
- Score too permissive
- Correct score but bad explanation
- Missing key risk
- Wrong main issue
- Bad fix recommendation
- Species count wording problem
- Overweighting cleanup crew
- Underweighting active swimmers

## Feature Request

Use this when TankFlare should add a new tool or improve an existing workflow.

Examples:

- More species
- More disease pages
- Better report export
- Saved correction history
- Public tank examples
- More water parameter logic
- Regional unit support
- Better beginner explanations
- More advanced keeper mode

## Maintainer Notes

TankFlare may not accept every correction.

A suggestion may be declined if:

- It lacks enough context
- It conflicts with stronger evidence
- It is too anecdotal
- It is unsafe
- It is copied from another source
- It does not fit TankFlare's current scope
- It needs more review
- It is correct but too specific for the current page/checker

Declined does not always mean "wrong." Sometimes it means "not enough evidence" or "not the right format yet."

## Current Goal

The current goal of this repo is to build a public review loop around TankFlare while the main app remains private.

In plain terms:

- Users can report problems.
- Contributors can suggest corrections.
- The community can discuss edge cases.
- TankFlare can improve from public review.
- The private app stays protected until the project is ready to open-source more.

## Future Open Source Plans

TankFlare may become more open-source over time.

Possible future public components could include:

- Public contribution tooling
- Data validation scripts
- Non-sensitive content templates
- Static documentation
- Exported correction schemas
- Community moderation tools
- Public issue triage automation

The main application code, internal datasets, and checker/model logic are not public at this stage.

## Links

- Website: https://www.tankflare.com
- Stocking checker: https://www.tankflare.com/checker
- Symptom checker: https://www.tankflare.com/symptom-checker
- Species pages: https://www.tankflare.com/species
- Disease pages: https://www.tankflare.com/diseases
- Contact: https://www.tankflare.com/contact

## Thank You

TankFlare gets better when experienced fishkeepers point out what automated advice misses.

If you have a correction, disagreement, edge case, or source-backed improvement, please open an issue or pull request.
