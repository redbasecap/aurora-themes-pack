# 🌌 Aurora Themes Pack for Home Assistant

Three premium themes — **Aurora** (glassy dark), **Linen** (warm light), and **Obsidian** (true-black OLED) — with **8 cinematic animated backgrounds** and a **live in-HA customizer** that lets you change accent colors and effects without restarting.

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge)](https://github.com/hacs/integration)
[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=redbasecap&repository=aurora-themes-pack&category=theme)

🌐 **[Live preview & demo →](https://redbasecap.github.io/aurora-themes-pack/)**

---

## ✨ What you get

| Theme | Mood | Best for |
|---|---|---|
| **Aurora** | Glassy translucent dark | Tablets, wall dashboards |
| **Linen** | Warm cream + earth tones | Bright rooms, family panels |
| **Obsidian** | Pure black + neon accents | OLED displays, control rooms |
| **Aurora Live** | Aurora with live customizer | Any setup where you tweak often |

Each theme ships with:
- 8 animated backgrounds (Lava orbs, Aurora ribbons, Color mesh, Cyber grid, Deep cosmos, Tidal waves, Silk dunes, Soft bokeh)
- Glossy card treatment baked in
- Card hover lift + accent glow
- Theme-tuned shadows, sidebar, fonts

---

## 🚀 Install

### Option A — One-click via HACS (recommended)

1. Click the **Add to HACS** button above ☝️
2. Click **Download** in HACS
3. Add this to `configuration.yaml`:
   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```
4. Restart Home Assistant
5. Profile → **Theme** → pick Aurora, Linen, or Obsidian

### Option B — Manual

```bash
# Copy theme files into your HA config themes folder
mkdir -p /config/themes
cp themes/*.yaml /config/themes/
```

Then in `configuration.yaml`:
```yaml
frontend:
  themes: !include_dir_merge_named themes
```

Restart HA, then Profile → Theme.

---

## 🎨 Live customizer (optional — no restarts after setup)

The **Aurora Live** theme variant reads accent colors and effects from Home Assistant helpers, so you can change everything from a Lovelace card in real time.

**Required for animated backgrounds:** install [`card-mod`](https://github.com/thomasloven/lovelace-card-mod) from HACS → Frontend. The static themes (`aurora`, `linen`, `obsidian`) work without it; `aurora_live` needs card-mod to inject the `@keyframes` animation onto the page.

**Setup:**
1. Install `card-mod` from HACS → Frontend → search "card-mod" → Download.
2. Append the contents of [`helpers/customizer.yaml`](./helpers/customizer.yaml) to your `configuration.yaml`.
3. Restart Home Assistant once to register the helpers.
4. Pick **"Aurora Live"** from Profile → Theme.
5. Paste the Lovelace card YAML from `helpers/customizer.yaml` into any dashboard view.

From that point on, any change to a helper repaints every device instantly — no restarts, no file edits.

> **Tip:** Pair with a HACS color-picker card (search HACS for `lovelace-color-picker-card`) for a real swatch UI instead of typing hex codes.

---

## 🌠 Animated backgrounds

| Value | Effect |
|---|---|
| `orbs` | Lava-lamp blobs drifting in deep blur |
| `aurora` | Aurora-borealis ribbons with chromatic shimmer |
| `mesh` | Saturated 5-point gradient morphing slowly |
| `cyber` | Perspective-tilted neon grid + pulse glow |
| `cosmos` | Dense starfield + nebula clouds |
| `waves` | Silky horizontal swells from below |
| `dunes` | Diagonal silken layers like wind on sand |
| `bokeh` | Defocused light blobs floating |

Set via `input_select.theme_background_style` in the customizer card. Backgrounds are driven by your three accent colors.

---

## 📦 Repository structure

```
aurora-themes-pack/
├── themes/
│   ├── aurora.yaml          ← static dark glassy theme
│   ├── linen.yaml           ← static warm light theme
│   ├── obsidian.yaml        ← static true-black OLED theme
│   └── aurora-live.yaml     ← live-customizable Aurora variant
├── helpers/
│   └── customizer.yaml      ← input helpers + Lovelace card YAML
├── docs/
│   └── index.html           ← landing page (GitHub Pages)
├── hacs.json
├── LICENSE
└── README.md
```

---

## 📸 Screenshots

See the [landing page](https://redbasecap.github.io/aurora-themes-pack/) for live animated previews of every theme and background.

---

## License

MIT — see [LICENSE](./LICENSE).
