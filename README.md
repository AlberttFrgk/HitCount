<div align="center">

# Hit Count

**A real-time hit count overlay for osu! powered by [tosu](https://github.com/KotRikD/tosu)**

![Version](https://img.shields.io/badge/version-1.0.0-blue?style=flat-square)
![Compatible](https://img.shields.io/badge/compatible-tosu-orange?style=flat-square)
![Resolution](https://img.shields.io/badge/resolution-240×430-green?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-lightgrey?style=flat-square)

Displays **PP · UR · Ratio · Hit Counts · Early/Late** for every osu! game mode in a clean, minimal overlay.  
Works as an in-game overlay or OBS browser source.  
Inspired by **[2ky](https://github.com/2ky1e)**'s mania hit count overlay.

<br>

| osu! standard | Taiko | Catch the Beat | Mania |
|:---:|:---:|:---:|:---:|
| ![osu](osu.png) | ![taiko](taiko.png) | ![catch](catch.png) | ![mania](mania.png) |

</div>

---

## Features

- **All four game modes** — osu! standard, Taiko, Catch the Beat, and Mania with correct hit labels per mode
- **Per-judgement Early/Late** — distributes early/late counts proportionally across each hit tier using precise hit error data
- **Live UR calculation** — computes Unstable Rate directly from the hit error array every frame
- **Ratio display** — shows good-hit to bad-hit ratio, adapts formula per mode (handles ∞:1 edge cases)
- **Mode-aware labels** — 300/100/50 for standard, Great/Ok for Taiko, Fruit/Drop/Droplet for Catch, MAX/Perfect/Great/Good/Bad for Mania
- **Toggleable sections** — hide PP, UR, Ratio, Hit Counts, Early/Late, or show Max Combo via settings
- **Per-element color customization** — set custom colors for labels and numbers for every judgement tier and mode
- **Layout options** — swap label/value column positions, adjust column widths, line height, and font
- **Auto-resets** — counters reset cleanly on retry, map change, or returning to menu
- **osu! Lazer support** — handles floating-point hit errors and object-shaped OD/mods data automatically

---

## Installation

1. **Download** this repository as a ZIP (or `git clone` it)
2. **Place** the folder inside your tosu `/static` directory
3. **Open** tosu and navigate to the overlay in your browser or OBS
4. **Configure** settings to your preference (see below)
5. **Add** the overlay URL as a Browser Source in OBS, or use it as an in-game overlay

> **Tip:** Set the browser source to **240×400** with a transparent background for best results.

---

## Settings

<details>
<summary><b>Global Settings</b></summary>

| Setting | Default | Description |
|---|---|---|
| Global Text Color | `#ffffff` | Base color for all text on the overlay |
| Swap Labels & Counters Position | `false` | Moves counters to the left and labels to the right |
| Font Name | `Arial` | Name of any font installed on Windows (e.g. Verdana, Arial) |
| Use Custom Font | `false` | Loads a custom font file from the overlay folder |
| Custom Font Filename | `font.ttf` | Filename of the custom font (e.g. `font.ttf`) |
| Label Column Width (px) | `130` | Width for text labels. If swapped, applies to the right side |
| Value Column Width (px) | `90` | Width for numbers. If swapped, applies to the left side |
| Line Height | `1.25` | Vertical spacing between rows (e.g. 1.25, 1.4) |

</details>

<details>
<summary><b>PP Settings</b></summary>

| Setting | Default | Description |
|---|---|---|
| Hide PP | `false` | Hides the PP display |
| Use Custom PP Colors | `false` | Enables specific colors for the PP row |
| PP Label Color | `#ffffff` | Color for the PP label |
| PP Number Color | `#ffffff` | Color for the PP value |

</details>

<details>
<summary><b>UR Settings</b></summary>

| Setting | Default | Description |
|---|---|---|
| Hide UR | `false` | Hides the Unstable Rate display |
| Use Custom UR Colors | `false` | Enables specific colors for the UR row |
| UR Label Color | `#ffffff` | Color for the UR label |
| UR Number Color | `#ffffff` | Color for the UR value |

</details>

<details>
<summary><b>Ratio Settings</b></summary>

| Setting | Default | Description |
|---|---|---|
| Hide Ratio | `false` | Hides the hit ratio display |
| Use Custom Ratio Colors | `false` | Enables specific colors for the Ratio row |
| Ratio Label Color | `#ffffff` | Color for the Ratio label |
| Ratio Number Color | `#ffffff` | Color for the Ratio value |

</details>

<details>
<summary><b>Max Combo Settings</b></summary>

| Setting | Default | Description |
|---|---|---|
| Hide Max Combo | `false` | Hides the max combo display |
| Use Custom Combo Colors | `false` | Enables specific colors for the Combo row |
| Combo Label Color | `#ffffff` | Color for the Combo label |
| Combo Number Color | `#ffffff` | Color for the Combo value |

</details>

<details>
<summary><b>Early / Late Settings</b></summary>

| Setting | Default | Description |
|---|---|---|
| Hide Early/Late | `false` | Hides the early and late hit counts |
| Use Custom Early/Late Colors | `true` | Enables specific colors for Early and Late rows |
| Early Label Color | `#0000ff` | Color for the Early label |
| Early Number Color | `#ffffff` | Color for the Early value |
| Late Label Color | `#ff0000` | Color for the Late label |
| Late Number Color | `#ffffff` | Color for the Late value |

</details>

<details>
<summary><b>Hit Counts Settings</b></summary>

| Setting | Default | Description |
|---|---|---|
| Hide Hit Counts | `false` | Hides 300g, 300, 200, 100, 50, and Miss counts |
| Use Custom Hit Count Label Colors | `true` | Enables specific colors for judgement labels |
| Use Custom Hit Count Number Colors | `false` | Enables specific colors for judgement numbers |

**osu! standard**

| Setting | Default |
|---|---|
| 300 Label Color | `#50b4ff` |
| 300 Number Color | `#50b4ff` |
| 100 Label Color | `#47e547` |
| 100 Number Color | `#47e547` |
| 50 Label Color | `#ffcc22` |
| 50 Number Color | `#ffcc22` |

**Taiko**

| Setting | Default |
|---|---|
| Great Label Color | `#ffcc22` |
| Great Number Color | `#ffcc22` |
| Ok Label Color | `#47e547` |
| Ok Number Color | `#47e547` |

**Catch the Beat**

| Setting | Default |
|---|---|
| Fruit Label Color | `#ffcc22` |
| Fruit Number Color | `#ffcc22` |
| Drop Label Color | `#47e547` |
| Drop Number Color | `#47e547` |
| Droplet Label Color | `#50b4ff` |
| Droplet Number Color | `#50b4ff` |

**Mania**

| Setting | Default |
|---|---|
| MAX Label Color | `#ffffff` |
| MAX Number Color | `#ffffff` |
| Perfect Label Color | `#ffcc22` |
| Perfect Number Color | `#ffcc22` |
| Great Label Color | `#47e547` |
| Great Number Color | `#47e547` |
| Good Label Color | `#50b4ff` |
| Good Number Color | `#50b4ff` |
| Bad Label Color | `#888888` |
| Bad Number Color | `#888888` |

**Miss (All Modes)**

| Setting | Default |
|---|---|
| Miss Label Color | `#ff0000` |
| Miss Number Color | `#ff0000` |

</details>

---

## How It Works

tosu streams live game data over WebSocket. The overlay subscribes to two endpoints simultaneously:

- **`/websocket/v2`** — hit counts, PP, mode, OD, mods, combo
- **`/websocket/v2/precise`** — raw `hitErrors` array for UR and per-judgement Early/Late

### Early/Late Calculation

Each new hit error is classified by its absolute millisecond value against the timing windows for the current mode and OD. Negative values are **Early**, positive values are **Late**. These tallies are then distributed proportionally across displayed hit rows using a delta-tracking system, so the on-screen Early/Late counts always sum correctly even when the hit error data arrives faster than display updates.

### Timing Windows

| Mode | Perfect | Formula |
|---|---|---|
| osu! standard | `80 − 6 × OD` ms | Good: `140 − 8 × OD` · Meh: `200 − 10 × OD` |
| Taiko | `50 − 3 × OD` ms | Ok: varies by OD ≥ 5 |
| Mania | `16 ms` (fixed) | Perfect: `64 − 3 × OD` · Great: `97 − 3 × OD` · … |
| Catch | — | Early/Late not shown |

> EZ halves OD · HR multiplies OD by 1.4 (capped at 10) before formulas are applied.

### Ratio Formula

| Mode | Formula |
|---|---|
| osu! standard | `300 / (100 + 50 + Miss)` |
| Taiko | `Great / (Ok + Miss)` |
| Catch | `Fruit / (Drop + Droplet + Miss)` |
| Mania | `MAX / (Perfect + Great + Good + Bad + Miss)` |

---

## File Structure

```
minimal-hit-count/
 index.html        # Overlay HTML
 main.css          # Styles & layout
 main.js           # WebSocket logic, UR, Early/Late, hit counts
 settings.json     # Plugin settings (read by tosu)
 metadata.txt      # Plugin metadata
 osu.png           # Preview — osu! standard
 taiko.png         # Preview — Taiko
 catch.png         # Preview — Catch the Beat
 mania.png         # Preview — Mania
```

---

## Compatibility

| | |
|---|---|
| **Overlay tool** | [tosu](https://github.com/KotRikD/tosu) (WebSocket v2 + v2/precise) |
| **Game modes** | osu! standard · Taiko · Catch the Beat · Mania |
| **Client** | Stable · Lazer |
| **Mods** | EZ · HR · DT / HT (rate-aware) |
| **OBS** | Browser Source, 240×430, transparent |

---

## Credits

- **Author** — [Albert](https://github.com/AlberttFrgk/)
- **Inspired by** — [2ky](https://github.com/2222zz/osu-custom-overlay)'s mania hit count overlay
- **Powered by** — [tosu](https://github.com/KotRikD/tosu) by KotRikD
