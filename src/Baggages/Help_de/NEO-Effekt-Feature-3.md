# Effekt-Feature-3

Boolesches Feature-Flag (Ein/Aus). **Bedeutung ist effektabhängig.**

### HSV→RGB (Rainbow) Zusatzfunktion

Für Effekte, die `FastLEDMath::hsv2rgb_rainbow(h,s,v, yellowBoost, greenCorr)` verwenden, ist Feature‑3
typischerweise als **„Green Correction“** gedacht.

**Hinweis zu Ausnahmen:** Wenn ein Effekt Feature‑2 bereits für einen Modus-Schalter belegt (z. B. Bounce/Rainbow/Variable Brightness),
kann es sein, dass Korrektur-Flags über Feature‑3 zusammengefasst oder nicht verfügbar sind. Siehe Tabelle unten.

## Effekt-spezifische Bedeutung

| Effekt | Bedeutung |
|---|---|
| **Rainbow (ID 2)** | enable green correction hooks (hsv2rgb_rainbow) |
| **Pride2015 (ID 3)** | enable green correction hooks (hsv2rgb_rainbow) |
| **Juggle (ID 5)** | green correction hooks (hsv2rgb_rainbow) |
| **RGBW_Test (ID 8)** | enable green correction hooks (hsv2rgb_rainbow) |
| **Sinelon (ID 13)** | enable HSV rainbow corrections (yellow/green hooks) |
| **Breathing (ID 16)** | enables HSV->RGB correction flags (yellow + green) |
| **Comet (ID 19)** | enable HSV rainbow correction hooks (yellow boost + green correction) |
| **Noise (ID 21)** | enable green correction hooks (hsv2rgb_rainbow) |
| **Lightning (ID 23)** | enable green correction hooks (hsv2rgb_rainbow) [only used in colored mode] |
| **Gradient (ID 24)** | enable green correction hooks (hsv2rgb_rainbow) |

| **Rainbow Cycle** | enable green correction hooks (hsv2rgb_rainbow) |



