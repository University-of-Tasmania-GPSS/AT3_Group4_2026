# Discussion

**30-minute access | 56 SA1s | Six service categories | Car vs public bus**

The map shows widespread **car advantage**, with lower dependency in parts of northern urban Burnie.

## From Highest to Lowest Car Dependency

Selected examples from the map, rather than a ranking of all SA1s. Scores are rounded as displayed.

| SA1 / example | CDI | Car access | Bus access | What it tells us |
| --- | ---: | ---: | ---: | --- |
| **60401107805** | **1.000** | **1.00** | **0** | Broad car access, bus access displayed as zero |
| **60401107601** | **1.000** | **0.77** | **0** | Strong car advantage, but less complete car access |
| **60401107604** | **1.000** | **0.01** | **0** | Very limited access even by car |
| **60401107704** | **0.994** | **1.00** | **0*** | Almost maximum car advantage |
| **60401107704** | **0.227** | **1.00** | **0.63** | Substantial bus access reduces the modal gap |

*Eastern SA1 identifier is obscured. Its bus score rounds to zero: CDI below 1 implies a small positive bus value. Another screenshot has obscured values and is not quantified.*

## Takeaways

::::{grid} 1 1 3 3

:::{grid-item}
:class: takeaway-car

**1. High CDI ≠ good access**

CDI = 1 occurs with car scores of **1.00, 0.77 and 0.01**.

Always read CDI alongside both accessibility scores.
:::

:::{grid-item}
:class: takeaway-bus

**2. Bus access narrows the gap**

In SA1 **60401107704**, bus access is **0.63** and CDI is **0.227**.

Car access remains higher, but the difference is smaller.
:::

:::{grid-item}
:class: takeaway-equity

**3. Equity needs IRSD**

**High CDI + low IRSD** identifies potential accessibility disadvantage.

Check IRSD and equity flags before identifying priority areas.
:::

::::

## What the Scores Measure

| Measure | Meaning | Does not establish |
| --- | --- | --- |
| **Accessibility, 0–1** | Average reachable proportion across six equally weighted service categories | Car ownership, percentage of residents served, or service quality |
| **Car score of 0.01** | Approximately 1% on the category-averaged scale | Exactly 1% of all destinations reachable |
| **CDI, −1 to +1** | Relative accessibility advantage: positive favours car, negative favours bus | How much access either mode provides on its own |

**Services:** schools · healthcare · pharmacies · supermarkets · greenspaces · leisure.

## What This Means for Burnie

| Pattern | Planning implication | Evidence to examine |
| --- | --- | --- |
| **High car access, little bus access** | Investigate bus connections to essential services | Routes, schedules, walking connections and journey times |
| **Limited access by both modes** | Examine broader service-access constraints | Origin locations, destination proximity and road connections |
| **High CDI with low IRSD** | Examine potential equity priorities | IRSD, population and the project's equity flags |

The northern concentration of services provides spatial context. The map alone cannot determine whether distance, waiting or transfers caused each accessibility gap.

## Limitations

| Model choice | Interpretation |
| --- | --- |
| **One origin per SA1** | Area-level estimate, not every household's experience |
| **30-minute threshold and scheduled bus conditions** | Results depend on travel-time limits and the modelled departure period |
| **Rounded popup values** | A displayed zero can hide a small positive score |
| **Selected screenshots** | Illustrate contrasts, not citywide statistics or confirmed IRSD overlap |

