# Effekt-Typ

Legt fest, welcher Animationseffekt auf dem Segment läuft.

## Implementierte Effekte (über EffectPool)

- **Solid (ID 0):** Statische Farbe ohne Animation
- **Wipe (ID 1):** Progressive Farbfüllung / Wisch-Effekt
- **Rainbow (ID 2):** Regenbogen-Farbverlauf (HSV->RGB)
- **Pride2015 (ID 3):** Pride2015 (FastLED) mit Helligkeitswellen
- **Confetti (ID 4):** Zufällige Farbpunkte mit Fade
- **Juggle (ID 5):** Mehrere Punkte, die sich kreuzen
- **BPM (ID 6):** Farbwellen im Takt (beats-per-minute)
- **Cylon (ID 7):** Knight Rider / Cylon Eye
- **RGBW_Test (ID 8):** RGBW Testpattern inkl. White-Kanal
- **GarageDoor (ID 9):** Garagentor-Animation (auf/zu)
- **Fire (ID 10):** Feuer/Flammen-Effekt
- **Theater Chase (ID 11):** Theater-Chase Lauflicht
- **Theater Chase Rainbow (ID 12):** Theater-Chase mit Regenbogenfarben
- **Sinelon (ID 13):** Sinus-Punkt mit Trail
- **Twinkle (ID 14):** Sternen-Funkeln
- **Sparkle (ID 15):** Schnelle Sparkles (Party)
- **Breathing (ID 16):** Atmen (smooth fade in/out)
- **Strobe (ID 17):** Stroboskop
- **Pulse (ID 18):** Pulse (Pulsieren)
- **Comet (ID 19):** Komet mit Schweif
- **Meteor (ID 20):** Meteor (Komet-Variante)
- **Noise (ID 21):** `inoise8()`-inspiriertes 1D-Noise (smooth)
- **Palette (ID 22):** `ColorFromPalette()`-ähnliche Paletten (Blend + Scroll)
- **Lightning (ID 23):** Blitz-Impulse (Flash + Decay)
- **Gradient (ID 24):** `fill_gradient()`-ähnlicher HSV‑Gradient

> Hinweis: Die **Index/ID-Reihenfolge** kann sich ändern, wenn Effekte per `NEOPIXEL_DISABLE_*` oder `NEOPIXEL_MINIMAL_EFFECTS` herauskompiliert werden.

## Parameter-Integration

- **Speed / Intensität:** universell verfügbar (je Effekt unterschiedlich interpretiert)
- **Option1–3:** effekt-spezifische Parameter
- **Reverse:** Richtungsumkehr (falls vom Effekt unterstützt)
- **Feature1–3:** boolesche Schalter (je Effekt belegt)


# NEO Effekt-Matrix

Diese Übersicht zeigt pro Effekt, wie die **ETS-Parameter** (Speed/Intensität/Option1–3/Feature1–3/Reverse) im aktuellen Code interpretiert werden.

> Hinweis: **Segment-Mirror** wird in der aktuellen Implementierung als `config.feature1=true` in die Effekt-Config gespiegelt.

> Hinweis: Für Effekte mit `hsv2rgb_rainbow(h,s,v, yellowBoost, greenCorr)` sind Feature2/Feature3 typischerweise **YellowBoost/GreenCorr** – außer wenn ein Effekt die Feature-Flags bereits für Modus-Schalter belegt.


| ID | Effekt | Speed | Intensität | Option1 | Option2 | Option3 | Reverse | Feature1 | Feature2 | Feature3 |
|---|---|---|---|---|---|---|---|---|---|---|
| 0 | **Solid** | - | - | - | - | - | - | - | - | - |
| 1 | **Wipe** | wipe step delay / animation speed | - | direction (0..5) (WipeDirection) | - | - | - | - | - | - |
| 2 | **Rainbow** | animation speed (time-based) | brightness (HSV V) | hue spacing / wavelength (0 => auto) | saturation (0 => 255) | phase / start hue offset | reverse direction | mirror | enable yellow brightness compensation (hsv2rgb_rainbow) | enable green correction hooks (hsv2rgb_rainbow) |
| 3 | **Pride2015** | - | - | - | - | - | - | - | - | - |
| 4 | **Confetti** | - | - | - | - | - | - | - | - | - |
| 5 | **Juggle** | movement speed (mapped to BPM base for beatsin) | master brightness (HSV V) | number of dots (0=default, 1..16) | fade speed (0=default, 1..50) higher = faster fade | hue offset / start hue | - | - | yellow brightness compensation (hsv2rgb_rainbow) | green correction hooks (hsv2rgb_rainbow) |
| 6 | **BPM** | - | - | - | - | - | - | - | - | - |
| 7 | **Cylon** | - | - | - | - | - | - | - | - | - |
| 8 | **SK6812Test** | - | - | - | - | - | - | - | - | - |
| 9 | **GarageDoor** | global speed scaling (0=auto/1.0x, otherwise 0.25x..3.0x) | master brightness scaling for all phase colors (0..255) | arrow size / trail length (0 = default) | runway group size (0 = default) | breathing speed override (0 = default) | reverse direction (arrows move inward, runway moves backward) | - | - | - |
| 10 | **Fire** | - | master brightness scaling (0..255) | cooling control (0=default, else 0..255 mapped to ~20..100) | sparking probability (0=default, else 0..255 mapped to ~50..200) | - | reverse direction (fire goes downwards) | - | blue fire mode (on/off) | - |
| 11 | **Theater Chase** | update interval (movement speed) | master brightness scaling for RGB | spacing (1..10, 0 => default 3) | dot size (1..5, 0 => default 1) | - | reverse chase direction | trail mode (fade instead of clear) | - | - |
| 12 | **Theater Chase Rainbow** | - | - | - | - | - | - | - | - | - |
| 13 | **Sinelon** | movement speed mapped to BPM (sine/bounce) | brightness scaling (HSV V / RGB scale) | fade rate control (0 => default) | dot size (0 => 1) | - | reverse direction (mirrors position) | rainbow mode (else uses configured RGB color) | bounce mode (linear bounce instead of sine) | enable HSV rainbow corrections (yellow/green hooks) |
| 14 | **Twinkle** | twinkle chance / activity level | - | - | - | - | - | - | - | - |
| 15 | **Sparkle** | - | - | - | - | - | - | - | - | - |
| 16 | **Breathing** | breathing speed (mapped to BPM) | max brightness (0 = off) | minimum brightness floor | curve shaping (0 = linear, 255 = more exponential) | - | - | hold at peak (pause at max) | rainbow mode (else fixed RGB color) | enables HSV->RGB correction flags (yellow + green) |
| 17 | **Strobe** | - | - | - | - | - | - | - | - | - |
| 18 | **Pulse** | - | - | - | - | - | - | - | - | - |
| 19 | **Comet** | - | - | - | - | - | - | - | - | - |
| 20 | **Meteor** | - | - | - | - | - | - | - | - | - |
| 21 | **Noise** | time evolution speed | master brightness (HSV V) | spatial scale (0 => default) | saturation (0 => 255) | hue offset | flips spatial direction | palette mode (0=HSV, 1=use fixed RGB config color modulated by noise) | enable yellow brightness compensation (hsv2rgb_rainbow) | enable green correction hooks (hsv2rgb_rainbow) |
| 22 | **Palette** | scroll speed (0 => very slow) | master brightness (scales RGB) | palette id (0..N-1) | blend (0=nearest, 1=linear) | index spacing (0 => auto-fit) | reverse scroll direction | auto palette cycle (periodic palette id advance) | - | - |
| 23 | **Lightning** | strike frequency / probability (0 => rare, 255 => frequent) | peak brightness (0..255) | strike width (0 => auto) | decay speed (0 => default) | hue for colored lightning (only if feature1=1) | reverses strike position mapping (mirrors position) | colored lightning (0 = white, 1 = use hue option3) | enable yellow brightness compensation (hsv2rgb_rainbow) [only used in colored mode] | enable green correction hooks (hsv2rgb_rainbow) [only used in colored mode] |
| 24 | **Gradient** | animation speed (phase shift over time; 0 => very slow) | brightness (HSV V) | start hue (0-255) | end hue (0-255) | saturation (0 => 255) | swaps gradient direction | - | enable yellow brightness compensation (hsv2rgb_rainbow) | enable green correction hooks (hsv2rgb_rainbow) |
