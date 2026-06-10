# TankFlare Condition File Template Guide

> **Please check out the [general contributing guide](https://github.com/Omo-star/tankflare-community/blob/main/CONTRIBUTING.md) first!**

If you want to add a condition, then it'll be reviewed and added to the TankFlare disease database if approved! **Beginners beware, this is a harder task!**

---

## Filename

Use lowercase letters, numbers, and hyphens only. No spaces.

```
fin-rot-tail-damage.json
velvet-oodinium.json
ich-like-white-spots.json
```

---

## Full annotated template

Each field is explained below with the JSON snippet for that field shown after.

### `id`
A unique identifier for this condition. Must be lowercase with underscores.
Use the same base name as the filename (hyphens become underscores).

```json
  "id": "fin_rot_tail_damage",
```

### `title`
The human-readable name shown in the app UI. Keep it concise but descriptive.

```json
  "title": "Fin rot and tail damage",
```

### `summary`
1–2 sentences. Describe what the fish looks like AND what is causing it.
A beginner reading this should immediately understand the condition.

```json
  "summary": "Fraying, ragged, or disintegrating fins caused by bacterial infection, usually Aeromonas or Pseudomonas. Most common in stressed fish kept in poor water conditions.",
```

### `urgency`
How fast the keeper needs to act. Pick exactly one:

| Value | Meaning |
|-------|---------|
| `"critical"` | Hours matter. Fish may die today without intervention. |
| `"high"` | Act within 24 hours. Condition will worsen quickly. |
| `"medium"` | Address within a few days. Not immediately life-threatening. |
| `"low"` | Monitor and correct environment. No emergency treatment needed. |

```json
  "urgency": "medium",
```

### `category`
The biological type of this condition. Pick exactly one:

| Value | Use for |
|-------|---------|
| `"parasite_like"` | Ich, velvet, flukes, anchor worms, fish lice |
| `"bacterial"` | Fin rot, columnaris, dropsy, popeye, septicemia |
| `"fungal"` | Cotton wool, saprolegnia |
| `"viral"` | Lymphocystis, KHV, iridovirus, VNN |
| `"water_quality"` | Ammonia, nitrite, nitrate, pH shock, chlorine |
| `"environmental"` | Temperature stress, oxygen depletion, CO2, voltage |
| `"behavioral_metabolic"` | Swim bladder, overfeeding, stress stripes, spawning |

```json
  "category": "bacterial",
```

### `confidenceLabel`
Tells the app how reliable a visual match is. Pick exactly one:

| Value | Meaning |
|-------|---------|
| `"pattern_match_not_diagnosis"` | Symptoms are non-specific. Many conditions look like this. |
| `"test_required_to_confirm"` | A water test or microscope is needed to confirm. |
| `"visual_diagnosis_possible"` | A trained eye can usually identify this from appearance alone. |

```json
  "confidenceLabel": "visual_diagnosis_possible",
```

---

### `symptomWeights`

Maps visible symptoms to a score. The app adds up the weights for every
symptom the user checks off. Higher weight = stronger signal for this condition.

**Weight scale:**
- `8–9` — Nearly diagnostic on its own (e.g., white salt-grain spots = ich)
- `5–7` — Strongly associated with this condition
- `3–4` — Moderately associated; helps confirm alongside other symptoms
- `1–2` — Weakly associated; a minor supporting signal

**Only include symptoms that are actually relevant to this condition.**
Leave out symptoms that are unrelated or neutral.

Available symptom keys:
`white_spots`, `clamped_fins`, `gasping`, `gold_dust_shimmer`, `raised_scales`,
`fin_rot`, `cotton_patches`, `red_streaks`, `bloating`, `flashing`, `wasting`,
`pop_eye`, `gill_flaring`, `lesions`, `lethargy`, `bottom_sitting`, `color_fading`,
`not_eating`, `darting`, `hiding`, `visible_parasites`, `cottony_growths`,
`rapid_breathing`, `loss_of_balance`, `abnormal_swimming`, `ulcers`,
`hemorrhaging`, `feces_abnormal`, `single_fish_only`, `multiple_fish_affected`,
`sudden_death`, `frayed_fins`, `spinal_curvature`, `eye_cloudiness`, `mucus_excess`

```json
  "symptomWeights": {
    "fin_rot":       8,
    "frayed_fins":   7,
    "red_streaks":   4,
    "lethargy":      3,
    "color_fading":  2,
    "not_eating":    2,
    "clamped_fins":  2
  },
```

---

### `riskFactorWeights`

Risk factors are things about the tank setup or history that make this condition
more likely. A user who just added new fish with no quarantine gets a higher score
for parasites, for example.

Same weight scale as symptoms (1–9).

Available risk factor keys:
`new_livestock_14d`, `no_quarantine`, `multiple_fish_affected`, `chronic_poor_water`,
`new_tank_under_8wk`, `overstock`, `high_feeding`, `all_fish_affected`,
`power_outage`, `recent_treatment`, `activated_carbon_removed`, `poor_ventilation`,
`saltwater_tank`, `freshwater_tank`, `koi_pond`, `live_plants`,
`invertebrates_present`, `scale_less_species`, `known_aggressor`,
`recent_decor_change`, `substrate_disturbed`, `shared_equipment`

```json
  "riskFactorWeights": {
    "chronic_poor_water":  6,
    "overstock":           4,
    "high_feeding":        3,
    "new_tank_under_8wk":  3
  },
```

---

### `negativeWeights`

Symptoms that argue *against* this condition. If a user checks these off,
the score goes down. Use negative integers.

- `-1 to -2` — Mildly argues against
- `-3 to -4` — Strongly argues against

Example: if you see white salt-grain spots, it's probably ich, not fin rot.
So fin rot gets a penalty when `white_spots` is checked.

```json
  "negativeWeights": {
    "white_spots":       -3,
    "cotton_patches":    -2,
    "visible_parasites": -3,
    "raised_scales":     -2,
    "bloating":          -2
  },
```

---

### `waterModifiers`

Water test results that adjust the score. Unlike symptoms (which are visual),
these come from actual test kit readings. They can carry higher weight (up to 10)
because test results are more objective than visual observation.

The `note` field is shown to the user in the app, so write it in plain English
as if you are explaining it to a beginner.

Available water parameter keys:
`ammonia_above_zero`, `nitrite_above_zero`, `nitrate_above_40`, `nitrate_above_80`,
`ph_below_6`, `ph_above_8_5`, `ph_rapid_change`, `temp_below_65f`, `temp_above_86f`,
`temp_rapid_change`, `dissolved_oxygen_low`, `chlorine_present`

```json
  "waterModifiers": {
    "ammonia_above_zero": {
      "weight": 5,
      "note": "Ammonia damages the slime coat and fins, making fish far more vulnerable to bacterial infection."
    },
    "nitrate_above_40": {
      "weight": 3,
      "note": "Chronically elevated nitrate suppresses the immune system and is a common underlying cause of fin rot."
    }
  },
```

---

### `immediateActions`

A short list of things the keeper should do RIGHT NOW, before reading anything else.
Write in plain English. Use complete sentences. No jargon.

Aim for 4–7 items. These are the most important, time-sensitive steps.

```json
  "immediateActions": [
    "Test your water for ammonia, nitrite, and nitrate. Poor water quality is the most common cause of fin rot.",
    "Perform a 25–30% water change with dechlorinated water at the same temperature as the tank.",
    "Remove any dead plant matter, uneaten food, or debris from the substrate.",
    "Increase water changes to every 2–3 days until the fins begin to heal.",
    "Quarantine the affected fish if other fish are showing signs of nipping at its fins."
  ],
```

---

### `protocols`

Step-by-step treatment plans. You can have multiple protocols for different
severity levels or different treatment approaches. Each protocol has:

- `title`: Short name for this treatment approach
- `steps`: The actual instructions, in order. Each step is one sentence or action.
- `cautions`: Warnings the user must read. Things that can go wrong, species
  sensitivities, medication interactions, etc.

```json
  "protocols": [
    {
      "title": "Mild fin rot: improve conditions first",
      "steps": [
        "Correct all water quality issues before adding any medication.",
        "Increase the frequency of water changes to every 2 days.",
        "Lightly salt the tank at 1 teaspoon per gallon if all species can tolerate salt. This helps fight bacteria and reduces osmotic stress.",
        "Add an Indian almond leaf or two, which release tannins that have mild antibacterial properties.",
        "Monitor fins daily. Mild fin rot often heals on its own once water quality improves.",
        "Give it 1–2 weeks before escalating to antibiotics if fins are not visibly improving."
      ],
      "cautions": [
        "Do not use salt with scaleless fish (corydoras, loaches, plecos) or sensitive species. It can harm them.",
        "Heavily planted tanks may not tolerate salt well either."
      ]
    },
    {
      "title": "Moderate to severe fin rot: antibiotic treatment",
      "steps": [
        "Move the affected fish to a quarantine tank before treating with antibiotics.",
        "Treat with kanamycin or nitrofurazone, following the package dosing instructions exactly.",
        "Perform a 25% water change before each new dose.",
        "Complete the full treatment course (usually 5–10 days) even if fins look better sooner.",
        "After treatment, return fish only after confirming water quality is stable."
      ],
      "cautions": [
        "Antibiotics will kill beneficial bacteria. Do not treat in your main tank unless absolutely necessary.",
        "Remove activated carbon from the filter before medicating. Carbon absorbs medication and makes it ineffective.",
        "Never mix antibiotics without guidance. Some combinations are harmful to fish.",
        "Scaleless fish (loaches, catfish) are more sensitive to medications. Reduce dose by 25–50% and monitor closely."
      ]
    }
  ],
```

---

### `whenToEscalate`

Conditions that mean things have gotten worse and the keeper needs to take
more serious action (consult a vet, euthanize, treat as a different condition, etc.).

Write these as clear observable signs, not vague warnings.

```json
  "whenToEscalate": [
    "The fin rot has reached the body of the fish, creating open ulcers or holes in the flesh.",
    "Red streaking is spreading from the fins toward the body, suggesting systemic bacterial infection.",
    "Fish is not responding to antibiotic treatment after a full course.",
    "Multiple fish in the tank are developing fin rot simultaneously despite good water quality.",
    "Fish stops eating entirely for more than 5 days."
  ],
```

---

### `sourceNotes`

List 1–3 references. These are shown in the app so users can learn more.

Rules:
- Only use real, working URLs. Do not make up specific article paths.
- If you are citing a university extension or research institution, link to the
  homepage or department page, not a specific article URL you are not sure about.
- Prefer `.edu`, `.gov`, or well-known aquarium health resources.
- The `note` field should explain in one sentence what this source covers and
  why it is useful.

```json
  "sourceNotes": [
    {
      "label": "UF/IFAS Aquatic Animal Health",
      "url": "https://edis.ifas.ufl.edu/",
      "note": "University of Florida extension publications on fish disease diagnosis and treatment."
    },
    {
      "label": "Merck Veterinary Manual: Fin Rot",
      "url": "https://www.merckvetmanual.com/exotic-and-laboratory-animals/aquarium-fish",
      "note": "Clinical overview of bacterial fin diseases in ornamental fish."
    }
  ]
```

---

## Complete blank template (copy this)

```json
{
  "id": "",
  "title": "",
  "summary": "",
  "urgency": "high",
  "category": "bacterial",
  "confidenceLabel": "visual_diagnosis_possible",
  "symptomWeights": {},
  "riskFactorWeights": {},
  "negativeWeights": {},
  "waterModifiers": {},
  "immediateActions": [],
  "protocols": [
    {
      "title": "",
      "steps": [],
      "cautions": []
    }
  ],
  "whenToEscalate": [],
  "sourceNotes": [
    {
      "label": "",
      "url": "",
      "note": ""
    }
  ]
}
```

---

## Quick checklist before saving

- [ ] `id` matches the filename (hyphens in filename = underscores in id)
- [ ] No em dashes anywhere (use a period and new sentence instead)
- [ ] All URLs are real and have been verified in a browser
- [ ] Weight values are integers (not decimals)
- [ ] No symptoms in `symptomWeights` that are also in `negativeWeights`
- [ ] File is valid JSON (paste into jsonlint.com to check)
- [ ] At least one protocol with at least 3 steps
- [ ] `urgency` is one of: `critical`, `high`, `medium`, `low`
