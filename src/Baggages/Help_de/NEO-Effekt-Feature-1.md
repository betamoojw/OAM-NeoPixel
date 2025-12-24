# Effekt-Feature-1

Boolesches Feature-Flag (Ein/Aus). **Bedeutung ist effektabhängig.**

> Hinweis: Es gibt zusätzlich einen **Segment-Parameter „Mirror Effekt“**.  
> In der aktuellen Implementierung wird Segment-Mirror als `config.feature1=true` in die Effekt-Config gespiegelt,
> damit Effekte, die „Mirror“ unterstützen, ohne Speziallogik funktionieren.

## Effekt-spezifische Bedeutung

| Effekt | Bedeutung |
|---|---|
| **Rainbow (ID 2)** | mirror |
| **Theater Chase (ID 11)** | trail mode (fade instead of clear) |
| **Sinelon (ID 13)** | rainbow mode (else uses configured RGB color) |
| **Breathing (ID 16)** | hold at peak (pause at max) |
| **Comet (ID 19)** | bounce mode (restart vs bounce at ends) |
| **Noise (ID 21)** | palette mode (0=HSV, 1=use fixed RGB config color modulated by noise) |
| **Palette (ID 22)** | auto palette cycle (periodic palette id advance) |
| **Lightning (ID 23)** | colored lightning (0 = white, 1 = use hue option3) |


