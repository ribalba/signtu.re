# The Carbon Footprint of Email Signatures
*(An illustrative calculation of how much additional CO₂-equivalent is caused solely by the use of email signatures.)*

---

## How many emails actually carry a signature?
| Step | Figure | Source | Comment |
|------|--------|--------|---------|
| Global emails sent/received per day (2025) | **376.4 billion** | Statista via EmailToolTester | — |
| Share filtered as spam (2023-24 average) | **46 %** | Cisco Talos Intelligence | ≈ 160 bn spam mails/day |
| Legitimate messages | **203 billion/day** | Calculation | 376.4 bn × (1 – 0.46) |
| Users who add a signature to at least one account | **~90 %** | HubSpot survey | — |
| Estimated share of legitimate mail that carries a designed signature | **60 %** | Assumption (business-mail ratios) | — |

**Result → ≈ 122 billion emails per day arrive with an appended signature.**

---

## How big is a typical signature?
| Type of signature | Typical weight* |
|-------------------|-----------------|
| *Lean* – text + compressed logo | **≈ 22 kB** |
| *Rich* – logo + head-shot + banner | **≈ 80 kB** |

\*On-disk sizes. Base-64 encoding during transmission adds ~33 %, but we keep the conservative raw sizes.

---

## CO₂-equivalent per unit of data transferred & stored
| Emissions factor | Derivation | Comment |
|------------------|------------|---------|
| **High-legacy:** 15 g CO₂e / MB | ADEME & The Shift Project | Includes device manufacture + older, dirtier grid |
| **Current-best:** 80 g CO₂e / GB (0.08 g / MB) | 0.194 kWh / GB (IEA) × 436 g CO₂ / kWh (2024 grid mix) | Reflects 2024 efficiencies & cleaner grid |

Using both factors shows today’s likely range.

---

## Daily **and** annual signature emissions (2025)

### Data volume
```
Signature-e-mails per day   = 122 bn
Extra bytes per e-mail      = 22–80 kB
--------------------------------------------------
Net extra data per day      = 2.6–9.3 PB
```
(1 PB ≈ 1 048 576 GB)

### Convert to CO₂e
| Scenario | g CO₂e / email | **t CO₂e / day** | **Mt CO₂e / year** |
|----------|---------------|------------------|--------------------|
| **Low** – lean sig + current factor | 0.002 g | 0.23 t | 0.08 Mt |
| **Moderate** – lean sig + high factor | **0.4 g** | **49 t** | **18 Mt** |
| **High** – rich sig + high factor | **1.2 g** | **146 t** | **53 Mt** |

### What does that mean?
* Even with present-day efficiencies, the **marketing-signature “tax” plausibly adds 20–50 million tonnes CO₂e each year** – comparable to the annual emissions of *Switzerland* or *New Zealand*.  
* If you apply the most up-to-date energy-intensity numbers, the footprint collapses to < 0.1 Mt; many corporate carbon calculators still default to the higher factors.

---

## Per-person perspective
For an office worker who sends **40 emails/day**:

| If their signature is… | Extra CO₂e each year |
|------------------------|----------------------|
| Lean (22 kB) & modern grid factor | **≈ 3 g** (negligible) |
| Lean but using older factor | **≈ 4 kg** |
| Rich (80 kB) & older factor | **≈ 12 kg** |

Removing a heavy signature is therefore about the same annual benefit as **driving ~50 km less** in a small petrol car.

---

## Key uncertainties & how to improve the estimate
1. **Energy-intensity of data traffic** keeps falling ~50 % every two years; pick factors that match your region and year.  
2. **Grid carbon intensity** varies five-fold between regions; hosting on 100 % renewables slashes emissions further.  
3. **Behavioural patterns** (reply chains, clients that strip images, local caching) can lower the bytes actually travelling.  
4. **Storage vs. transmission** – this calculation treats storage as negligible; if every copy is retained for years in high-availability storage, add ≈ 0.1 kWh per GB per year.

