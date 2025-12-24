# Effekt-Feature-2

Boolesches Feature-Flag (Ein/Aus). **Bedeutung ist effektabhängig.**

### HSV→RGB (Rainbow) Zusatzfunktion

Für Effekte, die `FastLEDMath::hsv2rgb_rainbow(h,s,v, yellowBoost, greenCorr)` verwenden, ist Feature‑2
typischerweise als **„Yellow Brightness Compensation“** gedacht.

## Effekt-spezifische Bedeutung

| Effekt | Bedeutung |
|---|---|
| **Rainbow (ID 2)** | enable yellow brightness compensation (hsv2rgb_rainbow) |
| **Pride2015 (ID 3)** | enable yellow brightness compensation (hsv2rgb_rainbow) |
| **Juggle (ID 5)** | yellow brightness compensation (hsv2rgb_rainbow) |
| **RGBW_Test (ID 8)** | enable yellow brightness compensation (hsv2rgb_rainbow) |
| **Fire (ID 10)** | blue fire mode (on/off) |
| **Sinelon (ID 13)** | bounce mode (linear bounce instead of sine) |
| **Breathing (ID 16)** | rainbow mode (else fixed RGB color) |
| **Comet (ID 19)** | rainbow mode (HSV rainbow instead of fixed RGB color) |
| **Noise (ID 21)** | value-only mode (0=hue+value, 1=value only) |
| **Lightning (ID 23)** | enable yellow brightness compensation (hsv2rgb_rainbow) [only used in colored mode] |
| **Gradient (ID 24)** | enable yellow brightness compensation (hsv2rgb_rainbow) |

| **Rainbow Cycle** | enable yellow brightness compensation (hsv2rgb_rainbow) |

