# JPT MOPA M7 100W: Master Pulse Width Testing Guide

This guide outlines a 4-Phase testing strategy for the JPT M7 100W MOPA laser. Because MOPA lasers require specific Frequency pairings for different Pulse Widths to maintain full wattage, these tables ensure you are testing at the 100W "Cutoff" for accurate results.

---

## 1. The MOPA "Cutoff" Reference Table
Before testing, ensure you use the correct **Cutoff Frequency**. Using a frequency lower than this will result in a linear drop in power; higher will maintain power but lower individual pulse energy.


| Pulse Width (ns) | Cutoff Frequency (kHz) | Primary Application |
| :--- | :--- | :--- |
| **2 - 6 ns** | 4000 kHz | Color, Frosting, Delicate Plastics |
| **9 - 13 ns** | 2500 - 3500 kHz | High Detail, Sensitive Materials |
| **20 - 30 ns** | 1000 - 1500 kHz | Anodized Black, High Speed Mark |
| **45 - 100 ns** | 300 - 660 kHz | Clean Engraving, Standard Marking |
| **150 - 250 ns** | 120 - 200 kHz | Deep Engraving, Hard Metals |
| **350 - 500 ns** | 67 - 85 kHz | Deep Ablation, Metal Cutting |

---

## 2. Testing Strategy: The 4-Phase Method
Run each phase as a separate test card. In each card, **Speed** and **Power** are your variables, while **Q-Pulse** and **Frequency** are locked to their optimal relationship.

### Phase 1: Surface & Color (Short Pulses)
*Best for: Stainless steel colors and titanium frosting.*
- **Static Pulse:** 4ns (Recommended)
- **Static Frequency:** 4000 kHz
- **Static Interval:** 0.001 mm – 0.005 mm
- **Focus:** Often best **2mm to 5mm Out of Focus**.


| Setting | Axis | Min | Max |
| :--- | :--- | :--- | :--- |
| **Speed** | **X-Axis** | 100 mm/s | 1000 mm/s |
| **Power** | **Y-Axis** | 10% | 50% |

### Phase 2: High-Contrast Marking (Medium Pulses)
*Best for: "True Black" on aluminum and high-speed marking on steel.*
- **Static Pulse:** 20ns or 30ns
- **Static Frequency:** 1000 kHz
- **Static Interval:** 0.01 mm – 0.03 mm
- **Focus:** Perfectly **In Focus**.


| Setting | Axis | Min | Max |
| :--- | :--- | :--- | :--- |
| **Speed** | **X-Axis** | 1000 mm/s | 4000 mm/s |
| **Power** | **Y-Axis** | 20% | 80% |

### Phase 3: Clean Engraving (Standard Pulses)
*Best for: Material removal with smooth floors and minimal burrs.*
- **Static Pulse:** 60ns or 80ns
- **Static Frequency:** 300 kHz – 500 kHz
- **Static Interval:** 0.02 mm – 0.05 mm
- **Focus:** Perfectly **In Focus**.


| Setting | Axis | Min | Max |
| :--- | :--- | :--- | :--- |
| **Speed** | **X-Axis** | 400 mm/s | 1500 mm/s |
| **Power** | **Y-Axis** | 30% | 100% |

### Phase 4: Deep Ablation (Long Pulses)
*Best for: Maximum material removal, coin making, and cutting.*
- **Static Pulse:** 200ns or 500ns
- **Static Frequency:** 67 kHz – 150 kHz
- **Static Interval:** 0.03 mm – 0.08 mm
- **Focus:** Start **In Focus**; use Z-Step for depths > 0.5mm.


| Setting | Axis | Min | Max |
| :--- | :--- | :--- | :--- |
| **Speed** | **X-Axis** | 100 mm/s | 800 mm/s |
| **Power** | **Y-Axis** | 60% | 100% |

---

## 3. Post-Test "Cleanup" Routine
To accurately see the results of engraving (Phases 3 & 4), run this cleanup pass over your test grid to remove soot:
- **Speed:** 3000 mm/s
- **Power:** 15% - 20%
- **Frequency:** 1000 kHz
- **Pulse Width:** 20ns
- **Interval:** 0.05 mm

---

## 4. Implementation in LightBurn
1. Use the **Material Test Generator** (Laser Tools > Material Test).
2. Set **Speed** on the X-axis and **Power** on the Y-axis using the ranges above.
3. Click **Edit Material Settings** to set the constant **Q-Pulse** and **Frequency** for that specific phase.
4. Run the test and label the physical card immediately.